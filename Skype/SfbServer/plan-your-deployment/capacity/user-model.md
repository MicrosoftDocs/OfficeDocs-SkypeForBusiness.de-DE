---
title: Nutzung des Benutzermodells für die Kapazitätsplanung für Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Dieser Artikel enthält Eine Anleitung dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, entsprechend der in den Benutzermodellen in Skype for Business Server beschriebenen Verwendung.
ms.openlocfilehash: b7222390f379bca79dfee7ab2e9f2c081118b22d635a1ef2edb2f1fc9ac0b70b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338113"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Nutzung des Benutzermodells für die Kapazitätsplanung für Skype for Business Server

Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, gemäß der verwendung, die in [Benutzermodellen in Skype for Business Server](user-models.md)beschrieben ist.

> [!NOTE]
> Für alle Empfehlungen in diesem Artikel wird davon ausgegangen, dass Sie Skype for Business kumulative Update vom November 2015 oder höher auf Ihren Servern installiert haben.

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Wir haben unsere Leistungstests auf der in der folgenden Tabelle beschriebenen Hardware durchgeführt. Alle unsere Empfehlungen und Ergebnisse basieren auf dieser Hardware. Wenn Sie versuchen möchten, weniger leistungsfähige Hardware als die hier aufgeführten zu verwenden, beachten Sie bitte, dass Sie möglicherweise mit Funktionalitätsproblemen oder einer schlechten Leistung konfrontiert sind. Diese Hardwareempfehlungen sind identisch mit Lync Server 2013, wenn dies hilfreich ist (und in Upgradeszenarien dies möglicherweise der Fall ist).

**Bei Leistungstests verwendete Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Hex-Core, 2,26 GHz oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server Serverrollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |8 oder mehr Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz. Zwei der Datenträger sollten RAID 1 verwenden, und sechs sollten RAID 10 verwenden.  <br/> - OR - <br/>Festkörperlaufwerke (SSDs), die eine Leistung ähnlich 8 mechanischen Festplattenlaufwerken mit 10.000 U/min bieten. <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 empfohlen, was eine Teamerstellung mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erfordert).  <br/> |

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

In der folgenden Tabelle sind unsere Empfehlungen zusammengefasst.

|**Serverrolle**|**Maximale Anzahl von unterstützten Benutzern**|
|:-----|:-----|
|Front-End-Pool mit zwölf Front-End-Servern und einem Back-End-Server oder einem gespiegelten Back-End-Serverpaar.  <br/> |80.000 eindeutige Benutzer gleichzeitig angemeldet, plus 50 % mehrfache Anwesenheitspunkte (Multiple Points of Presence, MPOP), die nicht mobile Instanzen darstellen, plus 40 % der Benutzer, die für Mobilität aktiviert sind, insgesamt 152.000 Endpunkte.  <br/> |
|A/V-Konferenzen  <br/> |Der von einem Front-End-Pool bereitgestellte A/V-Konferenzdienst unterstützt die Konferenzen des Pools mit einer maximalen Konferenzgröße von 250 Benutzern und jeweils nur einer derart großen Konferenzen.  <br/> **Hinweis:** Darüber hinaus können Sie große Konferenzen mit 250 bis 1.000 Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern zum Hosten der großen Konferenzen bereitstellen. Ausführliche Informationen finden Sie unter [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Ein Edgeserver  <br/> |12.000 gleichzeitige Remotebenutzer.  <br/> |
|Ein Director  <br/> |12.000 gleichzeitige Remotebenutzer.  <br/> |
|Überwachen und Archivieren  <br/> |Die Front-End-Dienste für die Überwachung und Archivierung werden auf jedem Front-End-Server und nicht auf separaten Serverrollen ausgeführt.  <br/> Für die Überwachung und Archivierung sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 oder höher ausführen, können Sie Ihre Archivierungsdaten in Exchange und nicht in einer dedizierten SQL-Datenbank speichern.  <br/> |
|Ein Vermittlungsserver  <br/> |Der Vermittlungsserver, der mit dem Front-End-Server verbunden ist, wird auf jedem Front-End-Server in einem Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen. Informationen zum eigenständigen Vermittlungsserver finden Sie im Abschnitt "Vermittlungsserver" weiter unten in diesem Thema.  <br/> |
|Ein Standard Edition-Server  <br/> |Es wird dringend empfohlen, wenn Sie Standard Edition Server zum Hosten von Benutzern verwenden, immer zwei Server verwenden, gepaart mit den Empfehlungen in [der Planung für hohe Verfügbarkeit und Notfallwiederherstellung.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery) Jeder Server im Paar kann bis zu 2.500 Benutzer hosten, und wenn ein Server ausfällt, kann der verbleibende Server 5.000 Benutzer in einem Failoverszenario unterstützen.  <br/>  Wenn Ihre Bereitstellung einen erheblichen Anteil an Audio- oder Videodatenverkehr umfasst, kann die Serverleistung mit mehr als 2.500 Benutzern pro Server beeinträchtigt werden. In diesem Fall sollten Sie weitere Standard Edition Server hinzufügen oder zu Skype for Business Server Enterprise Edition wechseln. <br/> |

## <a name="front-end-server"></a>Front-End-Server

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

In einem Front-End-Pool sollten Sie einen Front-End-Server für alle 6.660 Benutzer haben, die in Ihrem Pool verwaltet werden, vorausgesetzt, dass Hyperthreading auf allen Servern im Pool aktiviert ist und die Serverhardware die Empfehlungen in den [Serveranforderungen für Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md) oder [die Systemanforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)erfüllt. Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000. Dabei wird erneut vorausgesetzt, dass Hyperthreading auf allen Servern in Ihrem Pool aktiviert ist. Wenn Sie mehr als 80.000 Benutzer an einem Standort haben, können Sie mehr als einen Front-End-Pool bereitstellen.

Wenn Sie die Anzahl der Benutzer in einem Front-End-Pool berücksichtigen, schließen Sie alle Benutzer ein, die in Survivable Branch Appliances und Survivable Branch-Servern in Zweigstellen verwaltet werden, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. In einem Szenario mit 30.000 Benutzern und fünf Front-End-Servern müssen die Verbindungen von 6.000 Ihrer Benutzer auf die anderen vier verbleibenden Server übertragen werden, wenn ein Server nicht verfügbar ist. Diese vier verbleibenden Server haben dann jeweils 7.500 Benutzer. Dies ist eine größere Anzahl als empfohlen.

Wenn Sie stattdessen mit sechs Front-End-Servern für Ihre 30.000 Benutzer begonnen haben und einer nicht mehr verfügbar ist, müssen insgesamt 5.000 Benutzer zu den verbleibenden fünf Servern wechseln. Diese fünf verbleibenden Server hosten dann jeweils 6.000 Benutzer, was im empfohlenen Bereich liegt.

Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000. Die maximale Anzahl von Front-End-Servern in einem Pool beträgt 12.

Bei einem Front-End-Pool mit 80.000 Benutzern sind zwölf Front-End-Server in typischen Bereitstellungen, die den [Benutzermodellen in Skype for Business Server](user-models.md)folgen, leistungsbereit. Bei Bereitstellungen zur Unterstützung des Failovers für die Notfallwiederherstellung wird davon ausgegangen, dass maximal 40.000 Benutzer in jedem von zwei front-End-Paarpools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools zu enthalten, wenn ein Pool zu einem anderen Pool übergegangen werden muss.

Die Anzahl der Benutzer, die von einem bestimmten Front-End-Pool mit einer guten Leistung unterstützt werden, kann aus den folgenden Gründen von diesen Zahlen abweichen:

- Die Hardware für Ihre Front-End-Server entspricht nicht den Empfehlungen.

- Die Nutzung Ihrer Organisation unterscheidet sich stark von den Benutzermodellen, z. B. wenn Sie viel mehr Konferenzdatenverkehr haben.

Die folgende Tabelle zeigt die durchschnittliche Bandbreite für Chatnachrichten und Anwesenheitsinformationen, wenn das Benutzermodell angegeben ist, wie in [Benutzermodellen in Skype for Business Server](user-models.md)definiert.

|**Durchschnittliche Bandbreite pro Benutzer**|**Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern**|
|:-----|:-----|
|1,3 KBit/s  <br/> |13 MBit/s  <br/> |

> [!NOTE]
> Um die Medienleistung der gemeinsam installierten A/V-Konferenz- und Vermittlungsserverfunktionen auf Ihren Front-End-Servern zu verbessern, sollten Sie RSS (Receive-Side Scaling) auf den Netzwerkadaptern auf Ihren Front-End-Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie [unter Receive Side Scaling (RSS) in der dokumentation Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Angesichts des Benutzermodells, dass sich 5 % der Benutzer in einem Pool zu einem beliebigen Zeitpunkt in einer Konferenz befinden können, könnten in einem Pool von 80.000 Benutzern etwa 4.000 Benutzer gleichzeitig an Konferenzen teilnehmen. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z.B. nur Sofortnachrichten, Sofortnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine feste Grenze für die tatsächliche Anzahl der zulässigen Konferenzen, und die tatsächliche Nutzung bestimmt die tatsächliche Leistung. Wenn Ihre Organisation beispielsweise viel mehr Konferenzen im gemischten Modus hat, als im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server oder A/V-Konferenzserver bereitstellen als die empfehlungen in diesem Artikel. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

Die maximal unterstützte Konferenzgröße, die von einem regulären Skype for Business Server Front-End-Pool gehostet wird, in dem auch Benutzer gehostet werden, beträgt 250 Teilnehmer. Während eine Konferenz mit 250 Benutzern stattfindet, unterstützt der Pool auch andere Konferenzen, sodass sich insgesamt 5 % der Poolbenutzer an gleichzeitigen Konferenzen befinden. In einem Pool mit zwölf Front-End-Servern und 80.000 Benutzern, während die Konferenz mit 250 Benutzern stattfindet, unterstützt Skype for Business Server 3.750 andere Benutzer, die an kleineren Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die im Front-End-Pool oder Standard Edition Server verwaltet werden, unterstützt Skype for Business Server mindestens 125 andere Benutzer, die an kleineren Konferenzen im selben Pool oder Server teilnehmen, auf dem eine Konferenz mit 250 Benutzern gehostet wird.

Um Konferenzen mit 250 bis 1.000 Benutzern zu aktivieren, können Sie einen separaten Front-End-Pool einrichten, nur um diese Konferenzen zu hosten. In diesem Front-End-Pool werden keine Benutzer gehostet. Ausführliche Informationen finden Sie unter [Planen großer Besprechungen in Skype for Business Server.](../../plan-your-deployment/conferencing/large-meetings.md)

Wenn Ihre Organisation viel mehr Konferenzen im gemischten Modus hat, als im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server bereitstellen, als in diesem Dokument empfohlen wird (bis zu einem Grenzwert von 12 Front-End-Servern). Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

## <a name="edge-server"></a>Edgeserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Sie sollten einen Edgeserver für alle 12.000 Remotebenutzer bereitstellen, die gleichzeitig auf einen Standort zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Edgeservern empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver den Empfehlungen auf [Serverhardwareplattformen entspricht.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Wenn Sie die Anzahl von Benutzern für die Edgeserver berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

> [!NOTE]
> Zum Verbessern der Leistung des A/V-Konferenzedgediensts auf Ihren Edgeservern sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter Ihrer Edgeserver aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter["RSS (Receive Side Scaling) in Windows Server 2012".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="director"></a>Director

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie die Director-Serverrolle bereitstellen, wird empfohlen, einen Director für alle 12.000 Remotebenutzer bereitzustellen, die gleichzeitig auf eine Website zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Directors empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver den Empfehlungen auf [Serverhardwareplattformen entspricht.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Wenn Sie die Anzahl von Benutzern für die Director-Server berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

## <a name="mediation-server"></a>Vermittlungsserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie den Vermittlungsserver mit dem Front-End-Server verbinden, wird der Vermittlungsserver auf jedem Front-End-Server im Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen Vermittlungsserverpool bereitstellen, hängt die Anzahl der bereitzustellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für den Vermittlungsserver verwendeten Hardware, der Anzahl der voIP-Benutzer, die Sie haben, der Anzahl der Gatewaypeers, die jeder Vermittlungsserverpool steuert, des Datenverkehrs zur Nutzungsstunde über diese Gateways und des Prozentsatzes der Anrufe mit Medien, die den Vermittlungsserver umgehen.

Die folgenden Tabellen enthalten eine Richtlinie für die Anzahl gleichzeitiger Anrufe, die ein Vermittlungsserver verarbeiten kann, vorausgesetzt, dass die Hardware für die Vermittlungsserver die Anforderungen in [Serverhardwareplattformen](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) erfüllt und Hyperthreading aktiviert ist. Ausführliche Informationen zur Skalierbarkeit des Vermittlungsservers finden Sie unter ["Bewerten der VoIP-Nutzung und](estimating-voice-traffic.md) des Datenverkehrs für Skype for Business Server und [Bereitstellungsrichtlinien für den Vermittlungsserver in Skype for Business Server."](mediation-server-deployment-guidelines.md)

Alle folgenden Tabellen gehen davon aus, dass die Verwendung in [Benutzermodellen in Skype for Business Server](user-models.md)zusammengefasst ist.

**Kapazität des eigenständigen Vermittlungsservers: 70 % interne Benutzer, 30 % externe Benutzer mit Anrufkapazität ohne Umgehung (Medientranscodierung durch vermittlungsserver)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|**Maximale Anzahl von T1-Leitungen**|**Maximale Anzahl von E1-Leitungen**|
|:-----|:-----|:-----|:-----|
|Dualprozessor, Hex-Core, 2,26-GHz-Hyperthread-CPU **mit deaktiviertem Hyperthreading,** mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit dualem Port.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Dualprozessor, Hexadezimalkern, 2,26 GHz Hyperthread-CPU, mit 32 GB Arbeitsspeicher und einer Dualport-Netzwerkadapterkarte.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Für die Leistungstests wurden Server mit 32 GB Arbeitsspeicher verwendet. Für einen eigenständigen Vermittlungsserver werden jedoch auch Server mit 16 GB Arbeitsspeicher unterstützt, was für die in dieser Tabelle dargestellte Leistung auch ausreicht.

**Vermittlungsserverkapazität (Vermittlungsserver mit Front-End-Server verbunden) 70 % interne Benutzer, 30 % externe Benutzer, Anrufkapazität ohne Umgehung (Vom Vermittlungsserver durchgeführte Medienverarbeitung)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|
|:-----|:-----|
|Dualprozessor, Hexadezimalkern, 2,26 GHz Hyperthread-CPU mit 32 GB Arbeitsspeicher und 2 1 GB Netzwerkadapterkarten.  <br/> |150  <br/> |

> [!NOTE]
> Diese Zahl ist viel kleiner als die Zahlen für den eigenständigen Vermittlungsserver. Der Grund dafür ist, dass der Front-End-Server neben der für Sprachanrufe erforderlichen Transcodierung auch andere Features und Funktionen für die 6600 Benutzer verarbeiten muss, die darauf verwaltet werden.

> [!NOTE]
> Um die Leistung des Vermittlungsservers zu verbessern, sollten Sie RSS (Receive-Side Scaling) auf den Netzwerkadaptern auf Ihren Vermittlungsservern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter["Receive-Side Scaling in Windows Server 2012".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="back-end-server"></a>Back-End-Server

Obwohl ein Großteil der Datenbankinformationen in erster Linie auf den Front-End-Servern gespeichert wird, sollten Sie sicherstellen, dass Ihre Back-End-Server die weiter oben in diesem Abschnitt und in [den Serverhardwareplattformen aufgeführten](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)Hardwareempfehlungen erfüllen.

Um eine hohe Verfügbarkeit ihres Back-End-Servers zu gewährleisten, empfehlen wir die Bereitstellung von AlwaysOn-Verfügbarkeitsgruppen oder Serverspiegelung. Weitere Informationen finden Sie unter [Back-End-Server hohe Verfügbarkeit in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

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
|CPU  <br/> |64-Bit-Dualprozessor, Hex-Core, 2,26 GHz oder höher  <br/> |
|Arbeitsspeicher  <br/> |48 Gigabyte (GB)  <br/> |
|Datenträger  <br/> |25 Festplattenlaufwerke mit 10.000 U/min und 300 GB auf jedem Datenträger mit der Konfiguration in der folgenden Tabelle  <br/> |
|Netzwerk  <br/> | 1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 empfohlen, was teaming mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erfordert)  <br/> |

**Empfohlene Datenträgerkonfigurationen**

|**Laufwerk** <br/> |**RAID-Konfiguration** <br/> |**Anzahl der Datenträger** <br/> |
|:-----|:-----|:-----|
|KDS-, QoE- und Archivierungsdatenbankdatendateien auf einem einzelnen Laufwerk  <br/> |1+0  <br/> |16   <br/> |
|KDS-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|QoE-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|Archivierungsdatenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Kapazität des Video-Interoperabilität-Servers

Wenn Sie den Video-Interoperabilitätsserver bereitstellen und die Kapazität ermitteln müssen, sehen Sie sich die maximale Anzahl von Videotelekonferenzsystemen (Video Teleconferencing Systems, VTCs) an, die sich in gleichzeitigen Anrufen befinden. Wenn Sie beispielsweise 250 VTCs in Ihrer Organisation haben und Ihr Benutzermodell davon aus geht, dass maximal 20 % davon in gleichzeitigen Anrufen vorhanden sein können, basieren Sie ihre Kapazitätsplanung auf 50 gleichzeitigen VTCs.