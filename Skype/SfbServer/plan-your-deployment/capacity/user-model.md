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
description: Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, entsprechend der in den Benutzermodellen in Skype for Business Server beschriebenen Verwendung.
ms.openlocfilehash: e0b145ddfc766ba7db9012d4f3aaa7333f4f5d72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827635"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Kapazitätsplanung der Benutzermodellverwendung für Skype for Business Server

Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, entsprechend der in den Benutzermodellen in Skype for Business Server beschriebenen [Verwendung.](user-models.md)

> [!NOTE]
> Bei allen Empfehlungen in diesem Artikel wird davon ausgegangen, dass Sie das kumulative Update für Skype for Business vom November 2015 oder höher auf Ihren Servern installiert haben.

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Wir haben unsere Leistungstests auf der in der folgenden Tabelle beschriebenen Hardware durchgeführt. Alle unsere Empfehlungen und Ergebnisse basieren auf dieser Hardware. Wenn Sie versuchen, weniger leistungsfähige Hardware als die hier aufgeführte zu verwenden, beachten Sie, dass möglicherweise Funktionalitätsprobleme oder eine schlechte Leistung auftreten. Diese Hardwareempfehlungen sind mit Lync Server 2013 identisch, wenn dies hilfreich ist (und in Upgradeszenarien kann dies der Fall sein).

**Hardware, die bei Leistungstests verwendet wird**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Hexadezimalkern, 2,26 GHz oder höher.  <br/> Intel -Itanium-Prozessoren werden für Skype for Business Server-Serverrollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GIGABYTE (GB).  <br/> |
|Datenträger  <br/> |8 oder mehr Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz. Zwei datenträger sollten RAID 1 verwenden, und sechs sollten RAID 10 verwenden.  <br/> - ODER - <br/>Festkörperlaufwerke (Solid State Drives, SSDs), die eine ähnliche Leistung wie 8 mechanische Festplattenlaufwerke mit 10.000 U/min bieten. <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 GBit/s oder höher (2 werden empfohlen, was teaming mit einer einzigen MAC-Adresse und einer einzelnen IP-Adresse erfordert).  <br/> |

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

In der folgenden Tabelle sind unsere Empfehlungen zusammengefasst.

|**Serverrolle**|**Maximale Anzahl von unterstützten Benutzern**|
|:-----|:-----|
|Front-End-Pool mit zwölf Front-End-Servern und einem Back-End-Server oder einem gespiegelten Back-End-Serverpaar.  <br/> |80.000 eindeutige Benutzer gleichzeitig angemeldet, plus 50 % mehrere Anwesenheitspunkte (Multiple Points of Presence, MPOP), die nicht mobile Instanzen darstellen, plus 40 % der Benutzer, die für Mobilität für insgesamt 152.000 Endpunkte aktiviert sind.  <br/> |
|A/V-Konferenzen  <br/> |Der von einem Front-End-Pool bereitgestellte A/V-Konferenzdienst unterstützt die Konferenzen des Pools unter der Voraussetzung, dass eine maximale Konferenzgröße von 250 Benutzern und nur eine so große Konferenz gleichzeitig ausgeführt wird.  <br/> **Hinweis:** Darüber hinaus können Sie große Konferenzen mit 250 bis 1000 Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern zum Hosten der großen Konferenzen bereitstellen. Weitere Informationen finden Sie unter ["Planen großer Besprechungen in Skype for Business Server".](../../plan-your-deployment/conferencing/large-meetings.md)  <br/> |
|Ein Edgeserver  <br/> |12.000 gleichzeitige Remotebenutzer.  <br/> |
|Ein Director  <br/> |12.000 gleichzeitige Remotebenutzer.  <br/> |
|Überwachen und Archivieren  <br/> |Die Überwachungs- und Archivierungs-Front-End-Dienste werden auf jedem Front-End-Server und nicht auf separaten Serverrollen ausgeführt.  <br/> Für die Überwachung und Archivierung sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 oder höher ausführen, können Sie ihre Archivierungsdaten in Exchange und nicht in einer dedizierten SQL speichern.  <br/> |
|Ein Vermittlungsserver  <br/> |Der mit dem Front-End-Server ausgeführte Vermittlungsserver wird auf jedem Front-End-Server in einem Pool ausgeführt und sollte ausreichend Kapazität für die Benutzer im Pool bereitstellen. Informationen zu eigenständigen Vermittlungsservern finden Sie im Abschnitt "Vermittlungsserver" weiter später in diesem Thema.  <br/> |
|Ein Standard Edition-Server  <br/> |Es wird dringend empfohlen, bei Verwendung von Standard Edition-Servern zum Hosten von Benutzern immer zwei Server zu verwenden, gepaart mit den Empfehlungen in [Planning for High Availability and Disaster Recovery](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Jeder Server in diesem Paar kann bis zu 2.500 Benutzer hosten, und wenn ein Server ausfällt, kann der verbleibende Server 5.000 Benutzer in einem Failoverszenario unterstützen.  <br/>  Wenn Ihre Bereitstellung einen erheblichen Audio- oder Videodatenverkehr umfasst, kann die Serverleistung bei mehr als 2.500 Benutzern pro Server beeinträchtigen. In diesem Fall sollten Sie erwägen, weitere Standard Edition-Server hinzufügen oder zu Skype for Business Server Enterprise Edition zu verschieben. <br/> |

## <a name="front-end-server"></a>Front-End-Server

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

In einem Front-End-Pool sollte ein Front-End-Server pro 6.660 Benutzer in Ihrem Pool vorhanden sein, vorausgesetzt, dass Hyperthreading auf allen Servern im Pool aktiviert ist und die Serverhardware die Empfehlungen in den Serveranforderungen für [Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md) oder Systemanforderungen für Skype for Business Server  [2019](../../../SfBServer2019/plan/system-requirements.md)erfüllt. Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000, was wiederum davon ausgegangen wird, dass Hyperthreading auf allen Servern in Ihrem Pool aktiviert ist. Wenn Sie über mehr als 80.000 Benutzer an einem Standort verfügen, können Sie mehr als einen Front-End-Pool bereitstellen.

Wenn Sie die Anzahl der Benutzer in einem Front-End-Pool berücksichtigen, schließen Sie alle Benutzer ein, die in Survivable Branch Appliances und Survivable Branch Servers in Zweigstellen, die diesem Front-End-Pool zugeordnet sind, gespeichert sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. In einem Szenario mit 30.000 Benutzern und fünf Front-End-Servern, wenn ein Server nicht verfügbar ist, müssen die Verbindungen von 6.000 Benutzern auf die anderen vier verbleibenden Server übertragen werden. Diese vier verbleibenden Server haben dann jeweils 7.500 Benutzer, was eine größere Anzahl als empfohlen ist.

Wenn Sie stattdessen mit sechs Front-End-Servern für Ihre 30.000 Benutzer begonnen haben und einer nicht mehr verfügbar ist, müssen insgesamt 5.000 Benutzer auf die verbleibenden fünf Server umziehen. Diese fünf verbleibenden Server hosten dann jeweils 6.000 Benutzer, was im empfohlenen Bereich liegt.

Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000. Die maximale Anzahl von Front-End-Servern in einem Pool beträgt 12.

Bei einem Front-End-Pool mit 80.000 Benutzern sind zwölf Front-End-Server für die Leistung in typischen Bereitstellungen gut, die den Benutzermodellen [in Skype for Business Server folgen.](user-models.md) Bereitstellungen zur Unterstützung eines Failovers für die Notfallwiederherstellung setzen voraus, dass maximal 40.000 Benutzer in jedem der beiden Front-End-Paarpools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools zu enthalten, falls ein Failover eines Pools in den anderen pool erforderlich ist.

Die Anzahl von Benutzern, die von einem bestimmten Front-End-Pool mit einer guten Leistung unterstützt werden, kann aus folgenden Gründen von diesen Abweichen abweichen:

- Die Hardware für Ihre Front-End-Server erfüllt nicht die Empfehlungen.

- Die Nutzung In Ihrer Organisation wehen stark von den Benutzermodellen ab, z. B. wenn sie viel mehr Konferenzdatenverkehr haben.

Die folgende Tabelle zeigt die durchschnittliche Bandbreite für Chat und Anwesenheit, angesichts des Benutzermodells, wie in [Benutzermodellen in Skype for Business Server definiert.](user-models.md)

|**Durchschnittliche Bandbreite pro Benutzer**|**Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern**|
|:-----|:-----|
|1,3 KBit/s  <br/> |13 MBit/s  <br/> |

> [!NOTE]
> Zur Verbesserung der Medienleistung der Gemeinsamen A/V-Konferenz- und Vermittlungsserverfunktionen auf ihren Front-End-Servern sollten Sie rss (Receive-Side Scaling) auf den Netzwerkadaptern auf den Front-End-Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter [RSS (Receive Side Scaling) in Windows Server 2012 Dokumentation.](https://go.microsoft.com/fwlink/p/?LinkId=620365) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Angesichts des Benutzermodells, dass 5 % der Benutzer in einem Pool zu einem beliebigen Zeitpunkt an einer Konferenz teilnehmen können, kann ein Pool mit 80.000 Benutzern gleichzeitig etwa 4.000 Benutzer in Konferenzen haben. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z.B. nur Sofortnachrichten, Sofortnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl zulässiger Konferenzen, und die tatsächliche Nutzung bestimmt die tatsächliche Leistung. Wenn In Ihrer Organisation beispielsweise viel mehr Konferenzen im gemischten Modus als im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server oder A/V-Konferenzserver bereitstellen, als in diesem Artikel beschrieben. Details zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

Die maximal unterstützte Konferenzgröße, die von einem normalen Skype for Business Server-Front-End-Pool gehostet wird, der auch Benutzer hostet, beträgt 250 Teilnehmer. Während eine Konferenz mit 250 Benutzern ausgeführt wird, unterstützt der Pool weiterhin auch andere Konferenzen, so dass insgesamt 5 % der Poolbenutzer an gleichzeitigen Konferenzen teilnehmen. Beispielsweise unterstützt Skype for Business Server in einem Pool mit zwölf Front-End-Servern und 80.000 Benutzern während der Konferenz mit 250 Benutzern 3.750 weitere Benutzer, die an kleineren Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die im Front-End-Pool oder Standard Edition-Server gespeichert sind, unterstützt Skype for Business Server mindestens 125 andere Benutzer, die an kleineren Konferenzen im selben Pool oder Server teilnehmen, der eine Konferenz mit 250 Benutzern hosten soll.

Zum Aktivieren von Konferenzen mit 250 bis 1.000 Benutzern können Sie einen separaten Front-End-Pool zum Hosten dieser Konferenzen einrichten. Dieser Front-End-Pool hosten keine Benutzer. Weitere Informationen finden Sie unter ["Planen großer Besprechungen in Skype for Business Server".](../../plan-your-deployment/conferencing/large-meetings.md)

Wenn In Ihrer Organisation viel mehr Konferenzen im gemischten Modus als im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server bereitstellen, als in diesem Dokument empfohlen werden (bis zu einem Grenzwert von 12 Front-End-Servern). Details zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

## <a name="edge-server"></a>Edgeserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Sie sollten einen Edgeserver pro 12.000 Remotebenutzer bereitstellen, die gleichzeitig auf einen Standort zugreifen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Edgeservern empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [den Serverhardwareplattformen erfüllt.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Wenn Sie die Anzahl von Benutzern für die Edgeserver berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

> [!NOTE]
> Zum Verbessern der Leistung des A/V-Konferenzedgediensts auf Ihren Edgeservern sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter Ihrer Edgeserver aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter "[Receive Side Scaling (RSS) in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="director"></a>Director

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie die Director-Serverrolle bereitstellen, wird empfohlen, einen Director pro 12.000 Remotebenutzer, die gleichzeitig auf einen Standort zugreifen, bereitstellen. Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Directors empfohlen. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [den Serverhardwareplattformen erfüllt.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Wenn Sie die Anzahl von Benutzern für die Director-Server berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.

## <a name="mediation-server"></a>Vermittlungsserver

> [!NOTE]
> Gestreckte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie den Vermittlungsserver mit dem Front-End-Server verbinden, wird der Vermittlungsserver auf jedem Front-End-Server im Pool ausgeführt und sollte ausreichend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen Vermittlungsserverpool bereitstellen, hängt die Anzahl der zu bereitstellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für den Vermittlungsserver verwendeten Hardware, der Anzahl der voIP-Benutzer, der Anzahl von Gateway-Peers, die von jedem Vermittlungsserverpool kontrolliert wird, dem Datenverkehr zu gebuchten Stunden durch diese Gateways und dem Prozentsatz der Anrufe mit Medien, die den Vermittlungsserver umgeht.

Die folgenden Tabellen enthalten eine Richtlinie für die Anzahl gleichzeitiger Anrufe, die ein Vermittlungsserver verarbeiten kann, sofern die Hardware für die Vermittlungsserver die Anforderungen in [Serverhardwareplattformen](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) erfüllt und Hyperthreading aktiviert ist. Weitere Informationen zur Skalierbarkeit des Vermittlungsservers finden Sie unter "Schätzen der Sprachnutzung und des Datenverkehrs für [Skype for Business Server"](estimating-voice-traffic.md) sowie unter "Bereitstellungsrichtlinien für Vermittlungsserver in Skype for Business [Server".](mediation-server-deployment-guidelines.md)

In allen folgenden Tabellen wird von der Verwendung ausgegangen, wie in [den Benutzermodellen in Skype for Business Server zusammengefasst.](user-models.md)

**Kapazität des eigenständigen Vermittlungsservers: 70 % interne Benutzer, 30 % externe Benutzer mit Anrufkapazität ohne Umgehung (Medientranscodierung durch Vermittlungsserver)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|**Maximale Anzahl von T1-Leitungen**|**Maximale Anzahl von E1-Leitungen**|
|:-----|:-----|:-----|:-----|
|Dualprozessor, Sechskern, Hyperthreading-CPU mit 2,26 GHz und deaktivierter **Hyperthreading** mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Dualprozessor, Hexadezimalkern, Hyperthread-CPU mit 2,26 GHz, 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Für die Leistungstests wurden Server mit 32 GB Arbeitsspeicher verwendet. Für einen eigenständigen Vermittlungsserver werden jedoch auch Server mit 16 GB Arbeitsspeicher unterstützt, was für die in dieser Tabelle dargestellte Leistung auch ausreicht.

**Vermittlungsserverkapazität (Vermittlungsserver mit Front-End-Server) 70 % interne Benutzer, 30 % externe Benutzer, Anrufkapazität ohne Umgehung (Vom Vermittlungsserver ausgeführte Medienverarbeitung)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|
|:-----|:-----|
|Dualprozessor, Hexadezimalkern, Hyperthread-CPU mit 2,26 GHz und 32 GB Arbeitsspeicher und 2 Netzwerkadapterkarten mit 1 GB.  <br/> |150  <br/> |

> [!NOTE]
> Diese Zahl ist wesentlich kleiner als die für den eigenständigen Vermittlungsserver. Der Grund dafür ist, dass der Front-End-Server neben der für Sprachanrufe erforderlichen Transcodierung auch andere Features und Funktionen für die 6600 Benutzer verarbeiten muss, die auf dem Server gespeichert sind.

> [!NOTE]
> Um die Leistung des Vermittlungsservers zu verbessern, sollten Sie rss (Receive-Side Scaling) auf den Netzwerkadaptern auf den Vermittlungsservern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter "[Receive-Side Scaling in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="back-end-server"></a>Back-End-Server

Obwohl ein Teil der Datenbankinformationen hauptsächlich auf den Front-End-Servern gespeichert wird, sollten Sie sicherstellen, dass Ihre Back-End-Server die weiter oben in diesem Abschnitt und in den Serverhardwareplattformen aufgeführten [Hardwareempfehlungen erfüllen.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Um eine hohe Verfügbarkeit Ihres Back-End-Servers zu gewährleisten, empfehlen wir die Bereitstellung von AlwaysOn-Verfügbarkeitsgruppen oder Serverspiegelung. Weitere Informationen finden Sie unter [Back-End-Server hohe Verfügbarkeit in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

Wenn Sie die Überwachung oder Archivierung bereitstellen, wird die Front-End-Funktionalität dieser Dienste auf den Front-End-Servern ausgeführt. Überwachung und Archivierung verwenden jeweils einen eigenen Datenbankspeicher, getrennt vom Back-End-Speicher. Wenn Sie Exchange 2013 bereitgestellt haben, können Sie die Archivierungsdaten für Chatnachrichten in Exchange statt in einem dedizierten Speicher SQL speichern.

Die folgende Tabelle gibt an, wie viel Datenbankspeicher pro Benutzer und Tag für Überwachungs- und Archivierungsdaten erforderlich ist.

||**CDR (Überwachung)** <br/> |**QoE (Überwachung)** <br/> |**Archivierung** <br/> |
|:-----|:-----|:-----|:-----|
|Pro Benutzer und Tag erforderlicher Speicherplatz  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft hat die Hardware in der folgenden Tabelle für den Datenbankserver während der Leistungstests für die Überwachung und Archivierung verwendet. Bei den Tests wurden die Daten von zwei Front-End-Pools gesammelt, von denen jeder 80.000 Benutzer enthielt.

**Hardware, die beim Überwachen und Archivieren von Leistungstests verwendet wird**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Hexadezimalkern, 2,26 GHz oder höher  <br/> |
|Arbeitsspeicher  <br/> |48 GIGABYTE (GB)  <br/> |
|Datenträger  <br/> |25 Festplattenlaufwerke mit 10.000 U/min und 300 GB auf jedem Datenträger mit der Konfiguration in der folgenden Tabelle  <br/> |
|Netzwerk  <br/> | 1 Dual-Port-Netzwerkadapter, 1 GBit/s oder höher (2 werden empfohlen, für die ein Teaming mit einer einzigen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist)  <br/> |

**Empfohlene Datenträgerkonfigurationen**

|**Drive** <br/> |**RAID-Konfiguration** <br/> |**Anzahl der Datenträger** <br/> |
|:-----|:-----|:-----|
|CdR-, QoE- und Archivierungsdatenbankdatendateien auf einem einzigen Laufwerk  <br/> |1+0  <br/> |16   <br/> |
|KDS-Datenbankprotokolldatei  <br/> |1   <br/> |2   <br/> |
|QoE-Datenbankprotokolldatei  <br/> |1   <br/> |2   <br/> |
|Protokolldatei der Archivierungsdatenbank  <br/> |1   <br/> |2   <br/> |

## <a name="video-interop-server-capacity"></a>Kapazität des Video-Inop-Servers

Wenn Sie Video Interop Server bereitstellen und die Kapazität bestimmen müssen, sehen Sie sich die maximale Anzahl von Videotelekonferenzsystemen (VTCs) an, die gleichzeitig an Anrufen ausgeführt werden. Wenn Sie beispielsweise über 250 VTCs in Ihrer Organisation verfügen und Ihr Benutzermodell davon aus geht, dass nur 20 % davon gleichzeitige Anrufe ausführen können, können Sie ihre Kapazitätsplanung auf 50 gleichzeitige VTCsbasis verwenden.


