---
title: Kapazitätsplanung der Benutzermodellverwendung für Skype for Business Server
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
description: Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, entsprechend der Verwendung, die unter Benutzermodelle in Skype for Business Server beschrieben wird.
ms.openlocfilehash: a0fb1c193787f62e210f6d5bb7911ccfa40e5cf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118524"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Kapazitätsplanung der Benutzermodellverwendung für Skype for Business Server

Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, entsprechend der Verwendung, die [unter Benutzermodelle in Skype for Business Server beschrieben wird.](user-models.md)

> [!NOTE]
> Bei allen Empfehlungen in diesem Artikel wird davon ausgegangen, dass Sie kumulatives Skype for Business Update vom November 2015 oder höher auf Ihren Servern installiert haben.

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Wir haben unsere Leistungstests auf der in der folgenden Tabelle beschriebenen Hardware durchgeführt. Alle unsere Empfehlungen und Ergebnisse basieren auf dieser Hardware. Wenn Sie versuchen möchten, weniger leistungsfähige Hardware als die hier aufgeführten zu verwenden, beachten Sie bitte, dass möglicherweise Funktionsprobleme oder leistungsärmere Leistung auftreten. Diese Hardwareempfehlungen sind identisch mit Lync Server 2013, wenn dies hilfreich ist (und in Upgradeszenarien kann dies der Fall sein).

**Hardware, die in Leistungstests verwendet wird**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server-Serverrollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |8 oder mehr Festplatten mit 10.000 U/Min. mit mindestens 72 GB freiem Speicherplatz. Zwei der Datenträger sollten RAID 1 und sechs RAID 10 verwenden.  <br/> - OR - <br/>Solid State Drives (SSDs), die eine Ähnliche Leistung wie 8 mechanische Datenträgerlaufwerke mit 10.000 U/min bieten. <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 empfohlen, was eine Zusammenarbeit mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erfordert).  <br/> |

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

In der folgenden Tabelle sind unsere Empfehlungen zusammengefasst.

|**Serverrolle**|**Maximale Anzahl von unterstützten Benutzern**|
|:-----|:-----|
|Front-End-Pool mit zwölf Front-End-Servern und einem Back-End-Server oder einem gespiegelten Back-End-Serverpaar.  <br/> |80.000 eindeutige Benutzer gleichzeitig angemeldet, plus 50 % mehrere Anwesenheitspunkte (MPOP), die nicht mobile Instanzen darstellen, sowie 40 % der Benutzer, die für Mobilität für insgesamt 152.000 Endpunkte aktiviert sind.  <br/> |
|A/V-Konferenzen  <br/> |Der A/V-Konferenzdienst, der von einem Front-End-Pool bereitgestellt wird, unterstützt die Konferenzen des Pools unter der Annahme einer maximalen Konferenzgröße von 250 Benutzern und nur einer so großen Konferenz, die gleichzeitig ausgeführt wird.  <br/> **Hinweis:** Darüber hinaus können Sie große Konferenzen mit 250 bis 1000 Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern bereitstellen, um die großen Konferenzen zu hosten. Weitere Informationen finden Sie unter [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Ein Edgeserver  <br/> |12.000 gleichzeitige Remotebenutzer.  <br/> |
|Ein Director  <br/> |12.000 gleichzeitige Remotebenutzer.  <br/> |
|Überwachen und Archivieren  <br/> |Die Überwachungs- und Archivierungs-Front-End-Dienste werden auf jedem Front-End-Server statt auf separaten Serverrollen ausgeführt.  <br/> Überwachung und Archivierung erfordern immer noch eigene Datenbankspeicher. Wenn Sie auch Exchange 2013 oder höher ausführen, können Sie ihre Archivierungsdaten in Exchange und nicht in einer dedizierten SQL speichern.  <br/> |
|Ein Vermittlungsserver  <br/> |Vermittlungsserver, der mit Front-End-Server zusammenarbeitet, wird auf jedem Front-End-Server in einem Pool ausgeführt und sollte ausreichend Kapazität für die Benutzer im Pool bereitstellen. Eigenständige Vermittlungsserver finden Sie im Abschnitt "Vermittlungsserver" weiter weiter weiter in diesem Thema.  <br/> |
|Ein Standard Edition-Server  <br/> |Es wird dringend empfohlen, dass Sie, wenn Sie Standard Edition-Server zum Hosten von Benutzern verwenden, immer zwei Server verwenden, gepaart mit den Empfehlungen unter [Planning for High Availability and Disaster Recovery](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery). Jeder Server im Paar kann bis zu 2.500 Benutzer hosten, und wenn ein Server ausfällt, kann der verbleibende Server 5.000 Benutzer in einem Failoverszenario unterstützen.  <br/>  Wenn Ihre Bereitstellung einen erheblichen Audio- oder Videodatenverkehr umfasst, kann die Serverleistung bei mehr als 2.500 Benutzern pro Server darunter leiden. In diesem Fall sollten Sie erwägen, weitere Standard Edition-Server zu hinzufügen oder zu Skype for Business Server Enterprise Edition zu verschieben. <br/> |

## <a name="front-end-server"></a>Front-End-Server

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

In einem Front-End-Pool sollte ein Front-End-Server für jeweils 6.660 Benutzer in Ihrem Pool vorhanden sein, vorausgesetzt, dass hyperthreading auf allen Servern im Pool aktiviert ist und die Serverhardware die Empfehlungen in Serveranforderungen für [Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md) oder Systemanforderungen für Skype for Business Server  [2019](../../../SfBServer2019/plan/system-requirements.md)erfüllt. Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000, auch wenn hyperthreading auf allen Servern in Ihrem Pool aktiviert ist. Wenn Sie mehr als 80.000 Benutzer an einem Standort haben, können Sie mehrere Front-End-Pools bereitstellen.

Wenn Sie die Anzahl der Benutzer in einem Front-End-Pool berücksichtigen, schließen Sie alle Benutzer ein, die auf Survivable Branch Appliances und Survivable Branch Servers in Zweigstellen gespeichert sind, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. In einem Szenario mit 30.000 Benutzern und fünf Front-End-Servern müssen die Verbindungen von 6.000 Benutzern auf die anderen vier verbleibenden Server übertragen werden, wenn ein Server nicht verfügbar ist. Diese vier verbleibenden Server haben dann jeweils 7500 Benutzer, was eine größere Anzahl als empfohlen ist.

Wenn Sie stattdessen mit sechs Front-End-Servern für Ihre 30.000 Benutzer begonnen haben und einer nicht mehr verfügbar ist, müssen insgesamt 5.000 Benutzer auf die verbleibenden fünf Server wechseln. Diese fünf verbleibenden Server hosten dann jeweils 6000 Benutzer, die sich im empfohlenen Bereich befinden.

Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000. Die maximale Anzahl der Front-End-Server in einem Pool beträgt 12.

Für einen Front-End-Pool mit 80.000 Benutzern sind zwölf Front-End-Server für die Leistung gut, in typischen Bereitstellungen, die den [Benutzermodellen in Skype for Business Server folgen.](user-models.md) Bereitstellungen zur Unterstützung des Failovers für die Notfallwiederherstellung setzen voraus, dass maximal 40.000 Benutzer in jedem der beiden gekoppelten Front-End-Pools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools zu enthalten, falls ein Pool auf den anderen überfehlt werden muss.

Die Anzahl von Benutzern, die von einem bestimmten Front-End-Pool mit einer guten Leistung unterstützt werden, kann sich aus den folgenden Gründen von diesen Zahlen unterscheiden:

- Die Hardware für Ihre Front-End-Server erfüllt nicht die Empfehlungen.

- Die Nutzung Ihrer Organisation ist sehr unterschiedlich von den Benutzermodellen, z. B. wenn Sie viel mehr Konferenzdatenverkehr haben.

Die folgende Tabelle zeigt die durchschnittliche Bandbreite für Chat und Anwesenheit, wenn das Benutzermodell angegeben ist, wie unter [Benutzermodelle in Skype for Business Server definiert.](user-models.md)

|**Durchschnittliche Bandbreite pro Benutzer**|**Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern**|
|:-----|:-----|
|1,3 KBit/s  <br/> |13 MBit/s  <br/> |

> [!NOTE]
> Um die Medienleistung der gemeinsamen A/V-Konferenz- und Vermittlungsserverfunktionen auf Ihren Front-End-Servern zu verbessern, sollten Sie die empfangsseitige Skalierung (RSS) auf den Netzwerkadaptern auf den Front-End-Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie [unter Receive Side Scaling (RSS) in der Windows Server 2012 Dokumentation](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Angesichts des Benutzermodells, dass 5 % der Benutzer in einem Pool zu einem beliebigen Zeitpunkt an einer Konferenz teilnehmen können, könnte ein Pool von 80.000 Benutzern ungefähr 4.000 Benutzer gleichzeitig in Konferenzen haben. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z.B. nur Sofortnachrichten, Sofortnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl zulässiger Konferenzen, und die tatsächliche Nutzung bestimmt die tatsächliche Leistung. Wenn Ihre Organisation beispielsweise über viel mehr Konferenzen im gemischten Modus verfügt, als im Benutzermodell angenommen wird, müssen Sie möglicherweise mehr Front-End-Server oder A/V-Konferenzserver bereitstellen als die Empfehlungen in diesem Artikel. Weitere Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

Die maximal unterstützte Konferenzgröße, die von einem regulären Skype for Business Server-Front-End-Pool gehostet wird, der auch Benutzer hostet, beträgt 250 Teilnehmer. Während eine Konferenz mit 250 Benutzern ausgeführt wird, unterstützt der Pool weiterhin auch andere Konferenzen, so dass insgesamt 5 % der Poolbenutzer an gleichzeitigen Konferenzen teilnehmen. In einem Pool von zwölf Front-End-Servern und 80.000 Benutzern unterstützt Skype for Business Server beispielsweise während der Konferenz mit 250 Benutzern 3.750 andere Benutzer, die an kleineren Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die im Front-End-Pool oder auf dem Standard Edition-Server gespeichert sind, unterstützt Skype for Business Server mindestens 125 andere Benutzer, die an kleineren Konferenzen auf demselben Pool oder Server teilnehmen, der eine 250-Benutzer-Konferenz hosten.

Um Konferenzen mit 250 bis 1000 Benutzern zu ermöglichen, können Sie einen separaten Front-End-Pool einrichten, nur um diese Konferenzen zu hosten. In diesem Front-End-Pool werden keine Benutzer hosten. Weitere Informationen finden Sie unter [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Wenn In Ihrer Organisation viel mehr Konferenzen im gemischten Modus als im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server bereitstellen, als in diesem Dokument empfohlen wird (bis zu einem Grenzwert von 12 Front-End-Servern). Weitere Informationen zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

## <a name="edge-server"></a>Edgeserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Sie sollten einen Edgeserver für jeweils 12.000 Remotebenutzer bereitstellen, die gleichzeitig auf einen Standort zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Edgeservern empfohlen. In diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver den Empfehlungen in [Serverhardwareplattformen entspricht.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Wenn Sie die Anzahl von Benutzern für die Edgeserver berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

> [!NOTE]
> Zum Verbessern der Leistung des A/V-Konferenzedgediensts auf Ihren Edgeservern sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter Ihrer Edgeserver aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter "[Receive Side Scaling (RSS) in Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="director"></a>Director

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie die Director-Serverrolle bereitstellen, wird empfohlen, dass Sie einen Director für alle 12.000 Remotebenutzer bereitstellen, die gleichzeitig auf einen Standort zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Directors empfohlen. In diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver den Empfehlungen in [Serverhardwareplattformen entspricht.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Wenn Sie die Anzahl von Benutzern für die Director-Server berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

## <a name="mediation-server"></a>Vermittlungsserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie den Vermittlungsserver mit dem Front-End-Server verbinden, wird der Vermittlungsserver auf jedem Front-End-Server im Pool ausgeführt und sollte ausreichend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen Vermittlungsserverpool bereitstellen, hängt die Anzahl der zu bereitstellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für den Vermittlungsserver verwendeten Hardware, der Anzahl der VoIP-Benutzer, der Anzahl der Gateway-Peers, die von jedem Vermittlungsserverpool kontrolliert werden, dem Datenverkehr über diese Gateways zur Gebuchtzeit und dem Prozentsatz der Anrufe mit Medien, die den Vermittlungsserver umfahren.

Die folgenden Tabellen enthalten eine Richtlinie dazu, wie viele gleichzeitige Anrufe ein Vermittlungsserver verarbeiten kann, vorausgesetzt, dass die Hardware für die Vermittlungsserver die Anforderungen in [Serverhardwareplattformen](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) erfüllt und hyperthreading aktiviert ist. Weitere Informationen zur Skalierbarkeit des Vermittlungsservers finden Sie unter [Estimating voice usage and traffic for Skype for Business Server](estimating-voice-traffic.md) and Deployment guidelines for Mediation Server in Skype for Business [Server](mediation-server-deployment-guidelines.md).

In allen folgenden Tabellen wird von der Verwendung ausgegangen, wie unter [Benutzermodelle in Skype for Business Server zusammengefasst.](user-models.md)

**Eigenständige Vermittlungsserverkapazität: 70 % interne Benutzer, 30 % Externe Benutzer mit nicht umgehender Anrufkapazität (Medientranscodierung durch Vermittlungsserver)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|**Maximale Anzahl von T1-Leitungen**|**Maximale Anzahl von E1-Leitungen**|
|:-----|:-----|:-----|:-----|
|Dualprozessor, Hex Core, 2,26 GHz Hyperthread-CPU mit deaktivierter **Hyperthreadfunktion** mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Dualprozessor, Hex Core, Hyperthread-CPU mit 2,26 GHz, mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Für die Leistungstests wurden Server mit 32 GB Arbeitsspeicher verwendet. Für einen eigenständigen Vermittlungsserver werden jedoch auch Server mit 16 GB Arbeitsspeicher unterstützt, was für die in dieser Tabelle dargestellte Leistung auch ausreicht.

**Vermittlungsserverkapazität (Vermittlungsserver mit Front-End-Server) 70 % interne Benutzer, 30 % externe Benutzer, Nichtumgehung der Anrufkapazität (Medienverarbeitung durch Vermittlungsserver)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|
|:-----|:-----|
|Dualprozessor, Hex Core, Hyperthread-CPU mit 2,26 GHz, mit 32 GB Arbeitsspeicher und 2 1 GB Netzwerkadapterkarten.  <br/> |150  <br/> |

> [!NOTE]
> Diese Zahl ist viel kleiner als die Zahlen für den eigenständigen Vermittlungsserver. Der Grund dafür ist, dass der Front-End-Server neben der für Sprachanrufe erforderlichen Transcodierung weitere Features und Funktionen für die 6600 Benutzer verarbeiten muss, die auf dem Server gespeichert sind.

> [!NOTE]
> Um die Leistung des Vermittlungsservers zu verbessern, sollten Sie die empfangsseitige Skalierung (RSS) auf den Netzwerkadaptern auf den Vermittlungsservern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter "[Receive-Side Scaling in Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="back-end-server"></a>Back-End-Server

Obwohl ein Teil der Datenbankinformationen hauptsächlich auf den Front-End-Servern gespeichert wird, sollten Sie sicherstellen, dass ihre Back-End-Server den weiter oben in diesem Abschnitt und unter Serverhardwareplattformen aufgeführten Hardwareempfehlungen [entsprechen.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Um eine hohe Verfügbarkeit ihres Back-End-Servers zu gewährleisten, empfehlen wir die Bereitstellung von AlwaysOn-Verfügbarkeitsgruppen oder serverspiegelung. Weitere Informationen finden Sie unter [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

Wenn Sie Überwachung oder Archivierung bereitstellen, wird die Front-End-Funktionalität dieser Dienste auf den Front-End-Servern ausgeführt, Überwachung und Archivierung verwenden jeweils einen eigenen Datenbankspeicher, getrennt vom Back-End-Speicher. Wenn Sie Exchange 2013 bereitgestellt haben, können Sie auch Sofortnachrichtenarchivierungsdaten in Exchange speichern, anstatt in einem dedizierten SQL speichern.

In der folgenden Tabelle ist ungefähr angegeben, wie viel Datenbankspeicher pro Benutzer und Tag für Überwachungs- und Archivierungsdaten erforderlich ist.

||**CDR (Monitoring)** <br/> |**QoE (Monitoring)** <br/> |**Archivierung** <br/> |
|:-----|:-----|:-----|:-----|
|Pro Benutzer und Tag benötigter Speicherplatz  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft hat die Hardware in der folgenden Tabelle für den Datenbankserver für Überwachung und Archivierung während seiner Leistungstests verwendet. Bei den Tests wurden die Daten von zwei Front-End-Pools gesammelt, die jeweils 80.000 Benutzer enthielten.

**Hardware, die in Überwachungs- und Archivierungsleistungstests verwendet wird**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher  <br/> |
|Arbeitsspeicher  <br/> |48 GIGABYTE (GB)  <br/> |
|Datenträger  <br/> |25 Festplatten mit 10.000 U/Min. mit 300 GB auf jeder Festplatte, mit der Konfiguration in der folgenden Tabelle  <br/> |
|Netzwerk  <br/> | 1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 empfohlen, was eine Zusammenarbeit mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erfordert)  <br/> |

**Empfohlene Datenträgerkonfigurationen**

|**Laufwerk** <br/> |**RAID-Konfiguration** <br/> |**Anzahl der Datenträger** <br/> |
|:-----|:-----|:-----|
|CDR-, QoE- und Archivierungsdatenbankdatendateien auf einem einzigen Laufwerk  <br/> |1+0  <br/> |16   <br/> |
|KDS-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|QoE-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|Archivierungsdatenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Video interop Server-Kapazität

Wenn Sie Video Interop Server bereitstellen und die Kapazität ermitteln müssen, sehen Sie sich die maximale Anzahl von Video teleconferencing Systems (VTCs) an, die sich in gleichzeitigen Anrufen befinden. Wenn Sie beispielsweise über 250 VTCs in Ihrer Organisation verfügen und ihr Benutzermodell schätzt, dass sich 20 % davon in gleichzeitigen Anrufen begn nen, können Sie ihre Kapazitätsplanung auf 50 gleichzeitige VTCs verwenden.