---
title: Kapazitätsplanung Benutzermodell Verwendung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie auf einer Website benötigen, um die Anzahl der Benutzer auf dieser Website entsprechend der in den Benutzermodellen in Skype for Business Server beschriebenen Verwendung zu verwenden.
ms.openlocfilehash: f81989f463bb53f8eccc4d39b254560a7bc5bdf3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277580"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Kapazitätsplanung Benutzermodell Verwendung für Skype for Business Server

Dieser Artikel enthält Anleitungen dazu, wie viele Server Sie auf einer Website benötigen, um die Anzahl der Benutzer auf dieser Website entsprechend der in den [Benutzermodellen in Skype for Business Server](user-models.md)beschriebenen Verwendung zu verwenden.

> [!NOTE]
> Alle Empfehlungen in diesem Artikel gehen davon aus, dass Sie das kumulative Update für Skype for Business vom November 2015 oder ein jüngeres Update auf Ihren Servern installiert haben.

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Unsere Leistungstests wurden auf der in der Tabelle unten genannten Hardware durchgeführt. Alle unsere Empfehlungen und Ergebnisse beruhen auf dieser Hardware. Sofern Sie sich zur Verwendung einer weniger leistungsfähigen als der aufgeführten Hardware entschließen, seien Sie sich bewusst, dass unter Umständen Funktionalitätsprobleme oder Leistungseinbußen auftreten können. Diese Hardwareempfehlungen sind identisch mit lync Server 2013, wenn dies hilfreich ist (und in Aktualisierungsszenarien möglicherweise).

**Bei Leistungstests eingesetzte Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz.  <br/> Intel Itanium-Prozessoren werden für die Skype for Business Server-Serverrollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |8 oder mehr Festplatten mit 10.000 U/Min mit mindestens 72 GB freiem Speicher. Zwei Festplatten sollten RAID 1 verwenden und sechs Festplatten sollten RAID 10 verwenden.  <br/> – ODER – <br/>Solid State Drives (SSDs), die Leistung ähnlich wie mechanische Festplattenlaufwerke mit 8 10.000-rpm bieten. <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür ein Teamvorgang mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist).  <br/> |

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

Eine Übersicht über unsere Empfehlungen finden Sie in der folgenden Tabelle.

|**Serverrolle**|**Maximale Anzahl von unterstützten Benutzern**|
|:-----|:-----|
|Front-End-Pool mit zwölf Front-End-Servern und einem Back-End-Server oder einem gespiegelten Paar von Back-End-Servern.  <br/> |80.000 eindeutige Benutzer, plus 50 % Anmeldungen auf mehreren Geräten (Multiple Point Of Presence, MPOP), die keine mobilen Instanzen sind, plus 40 % Benutzer, die für Mobilität aktiviert sind, für insgesamt 152.000 Endpunkte.  <br/> |
|A/V-Konferenzen  <br/> |Der a/V-Konferenzdienst, der von einem Front-End-Pool bereitgestellt wird, unterstützt die Konferenzen des Pools, vorausgesetzt, es wird eine maximale Konferenzgröße von 250-Benutzern und nur eine solche große Konferenz gleichzeitig ausgeführt.  <br/> **Hinweis:** Darüber hinaus können Sie große Konferenzen zwischen 250-und 1000-Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern bereitstellen, um die umfangreichen Konferenzen zu hosten. Ausführliche Informationen finden Sie unter [Planen großer Besprechungen in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Ein Edgeserver  <br/> |12.000 Remotebenutzer gleichzeitig  <br/> |
|Ein Direktor  <br/> |12.000 Remotebenutzer gleichzeitig  <br/> |
|Überwachen und Archivieren  <br/> |Die Überwachungs-und Archivierungs-Front-End-Dienste werden auf jedem Front-End-Server und nicht auf separaten Server Rollen ausgeführt.  <br/> Für das Überwachen und Archivieren sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 oder höher ausführen, können Sie Ihre Archivierungsdaten in Exchange behalten, anstatt in einer dedizierten SQL-Datenbank.  <br/> |
|Ein Vermittlungs Server  <br/> |Der mit dem Front-End-Server zusammenhängende Vermittlungsserver wird auf jedem Front-End-Server in einem Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen. Informationen zum eigenständigen Vermittlungsserver finden Sie im Abschnitt "Mediation Server" weiter unten in diesem Thema.  <br/> |
|Ein Standard Edition-Server  <br/> |Wir empfehlen dringend, dass Sie bei der Verwendung von Standard Edition-Servern zum Hosten von Benutzern immer zwei Server verwenden, die mit den Empfehlungen [für die Planung von höchst Verfügbarkeit und Disaster Recovery](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx)kombiniert werden. Jeder Server der Kombination kann bis zu 2.500 Benutzer hosten und wenn ein Server ausfällt, kann der verbleibende Server in einem Failoverszenario 5.000 Benutzer unterstützen.  <br/>  Wenn in Ihrer Bereitstellung Audio- oder Videodatenverkehr im großen Umfang anfällt, wird die Serverleistung u. U. auch bei mehr als 2.500 Benutzern pro Server beeinträchtigt. In diesem Fall sollten Sie das Hinzufügen von weiteren Standard Edition-Servern oder das Umstieg auf Skype for Business Server Enterprise Edition in Frage stellen. <br/> |

## <a name="front-end-server"></a>Front-End-Server

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

In einem Front-End-Pool sollten Sie über einen Front-End-Server für alle 6.660-Benutzer verfügen, die in Ihrem Pool verwaltet werden, vorausgesetzt, dass Hyper-Threading auf allen Servern im Pool aktiviert ist und dass die Server Hardware die Empfehlungen in den [Server Anforderungen für Skype für erfüllt. Business Server 2015](../requirements-for-your-environment/server-requirements.md) oder [System Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 80.000, und es wird davon ausgegangen, dass Hyper-Threading auf allen Servern in Ihrem Pool aktiviert ist. Wenn Sie über mehr als 80.000 Benutzer an einer Website verfügen, können Sie mehr als einen Front-End-Pool bereitstellen.

Wenn Sie die Anzahl der Benutzer in einem Front-End-Pool berücksichtigen, schließen Sie alle Benutzer ein, die sich auf überlebensfähigen Branch Appliances und Überlebenden Verzweigungs Servern in Zweigniederlassungen befinden, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. In einem Szenario, in dem Sie 30.000-Benutzer und fünf Front-End-Server haben, müssen die Verbindungen von 6000 Ihrer Benutzer auf die anderen vier verbleibenden Server übertragen werden, wenn ein Server nicht verfügbar ist. Auf den übrigen vier Servern würden in diesem Fall je 7.500 Benutzer verwaltet, sodass die empfohlene Anzahl überschritten wäre.

Wenn Sie stattdessen mit sechs Front-End-Servern für ihre 30.000-Benutzer begonnen haben und eine nicht mehr zur Verfügung steht, müssen insgesamt 5000-Benutzer zu den restlichen fünf Servern wechseln. Diese fünf Server hosten dann jeweils 6.000 Benutzer, was im empfohlenen Bereich liegt.

Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 80.000. Die maximale Anzahl der Front-End-Server in einem Pool beträgt 12.

Bei einem Front-End-Pool mit 80.000-Benutzern sind zwölf Front-End-Server in typischen Bereitstellungen, die den [Benutzermodellen in Skype for Business Server](user-models.md)folgen, gut für die Leistung. Für Bereitstellungen zur Unterstützung von Disaster Recovery-Failover wird davon ausgegangen, dass maximal 40.000-Benutzer in jedem von zwei gekoppelten Front-End-Pools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools zu enthalten, falls ein Pool über t fehlerhaft sein muss. o der andere.

Die Anzahl der Benutzer, die mit einer guten Leistung von einem bestimmten Front-End-Pool unterstützt werden, kann aus folgenden Gründen von diesen Zahlen abweichen:

- Die Hardware für Ihre Front-End-Server entspricht nicht den Empfehlungen.

- Die Nutzung Ihrer Organisation unterscheidet sich stark von den Benutzermodellen, beispielsweise, wenn Sie viel mehr Konferenz Verkehr haben.

Die folgende Tabelle zeigt die durchschnittliche Bandbreite für Sofortnachrichten und Anwesenheitsinformationen anhand des Benutzermodells, wie es in den [Benutzermodellen in Skype for Business Server](user-models.md)definiert ist.

|**Durchschnittliche Bandbreite pro Benutzer**|**Bandbreitenanforderungen pro Front-End-Server mit 6.660-Benutzern**|
|:-----|:-----|
|1,3 KBit/s  <br/> |13 MBit/s  <br/> |

> [!NOTE]
> Wenn Sie die Medien Leistung der co-located A/V-Konferenz-und Vermittlungs Server Funktionalität auf Ihren Front-End-Servern verbessern möchten, sollten Sie auf den Netzwerkadaptern auf Ihren Front-End-Servern die Receive-Side-Skalierung (RSS) aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter [empfangen von Seitenskalierung (RSS) in der Windows Server 2012-Dokumentation](https://go.microsoft.com/fwlink/p/?LinkId=620365). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Bei einem Benutzermodell, bei dem 5 % der Benutzer in einem Pool gleichzeitig an einer Konferenz teilnehmen können, können in einem Pool mit 80.000 Benutzern gleichzeitig ca. 4.000 Benutzer an einer Konferenz teilnehmen. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z. B. nur Chatnachrichten, Chatnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl von zulässigen Konferenzen, die tatsächliche Leistung ist durch die tatsächliche Nutzung bestimmt. Wenn Ihre Organisation beispielsweise über viele weitere Konferenzen im gemischten Modus verfügt, als im Benutzermodell angenommen wird, müssen Sie möglicherweise mehr Front-End-Server oder A/V-Konferenzserver bereitstellen als die Empfehlungen in diesem Artikel. Details zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

Die maximale unterstützte Konferenzgröße, die von einem regulären Skype for Business Server-Front-End-Pool gehostet wird, der auch Nutzer hostet, ist 250 Teilnehmer. Während eine 250-Benutzer Konferenz stattfindet, unterstützt der Pool weiterhin auch andere Konferenzen, sodass sich insgesamt 5% der Pool Benutzer in parallelen Konferenzen befinden. In einem Pool von zwölf Front-End-Servern und 80.000-Benutzern, während die 250-User-Konferenz stattfindet, unterstützt Skype for Business Server 3.750 anderen Benutzern, die an kleineren Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die sich auf dem Front-End-Pool oder Standard Edition-Server befinden, unterstützt Skype for Business Server mindestens 125 anderen Benutzern, die an kleineren Konferenzen im gleichen Pool oder Server teilnehmen, der eine Konferenz mit 250-Benutzern hostet.

Zum Aktivieren von Konferenzen, die zwischen 250-und 1000-Benutzern vorhanden sind, können Sie einen separaten Front-End-Pool einrichten, um diese Konferenzen zu hosten. Dieser Front-End-Pool hostet keine Benutzer. Einzelheiten hierzu finden Sie unter [Planen großer Besprechungen in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Wenn in Ihrer Organisation viel mehr Konferenzen im gemischten Modus stattfinden, als im Benutzermodell angenommen werden, müssen Sie möglicherweise weitere Front-End-Server bereitstellen, als wir in diesem Dokument empfehlen (bis zu einem Grenzwert von 12 Front-End-Servern). Details zu den Annahmen im Benutzermodell finden Sie unter [Benutzermodelle in Skype for Business Server](user-models.md).

## <a name="edge-server"></a>Edgeserver

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Sie sollten einen Edgeserver für alle 12.000-Remotebenutzer bereitstellen, die gleichzeitig auf eine Website zugreifen. Wir empfehlen mindestens zwei Edge-Server für eine höhere Verfügbarkeit. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)erfüllt.

Wenn Sie die Anzahl der Benutzer für die Edgeserver berücksichtigen, schließen Sie die Benutzer, die sich auf Survivable Branch Appliances und überlebensfähige Verzweigungs Server befinden, in Zweigniederlassungen ein, die einem Front-End-Pool an diesem Standort zugeordnet sind.

> [!NOTE]
> Wenn Sie die Leistung des A/V-Konferenz-Edgedienst auf Ihren Edge-Servern verbessern möchten, sollten Sie auf den Netzwerkadaptern auf Ihren Edge-Servern die Receive-Side-Skalierung (RSS) aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie[unter "Receive Side Scale (RSS) in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="director"></a>Director

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie die Director-Serverrolle bereitstellen, empfehlen wir, dass Sie einen Director für alle 12.000-Remotebenutzer bereitstellen, die gleichzeitig auf eine Website zugreifen. Wir empfehlen mindestens zwei Directors für höchste Verfügbarkeit. Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)erfüllt.

Wenn Sie die Anzahl der Benutzer für die Directors berücksichtigen, fügen Sie die Benutzer, die sich auf Survival Branch-Appliances und überlebensfähige Branch-Server befinden, in Zweigniederlassungen ein, die einem Front-End-Pool an diesem Standort zugeordnet sind.

## <a name="mediation-server"></a>Vermittlungsserver

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie den Vermittlungsserver mit dem Front-End-Server collocate, wird der Mediation Server auf jedem Front-End-Server im Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen vermittlungsserverpool bereitstellen, hängt die Anzahl der bereitzustellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für den Vermittlungsserver verwendeten Hardware, der Anzahl der VoIP-Benutzer, der Anzahl der Gateway-Peers, die für jeden vermittlungsserverpool verwendet werden. Steuerelemente, der auslastungsstunden Verkehr über diese Gateways und der Prozentsatz von Anrufen mit Medien, die den Vermittlungs Server umgehen.

Die folgenden Tabellen enthalten eine Richtlinie für die Anzahl von gleichzeitigen anrufen, die ein Vermittlungsserver verarbeiten kann, vorausgesetzt, die Hardware für die Vermittlungsserver erfüllt die Anforderungen in [Server Hardwareplattformen](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) , und Hyper-Threading ist aktiviert. Details zur Skalierbarkeit von Mediations Servern finden Sie unter [schätzen der sprach Nutzung und des Datenverkehrs für Skype for Business Server](estimating-voice-traffic.md) und [Bereitstellungsrichtlinien für den Mediation Server in Skype for Business Server](mediation-server-deployment-guidelines.md).

Alle folgenden Tabellen gehen davon aus, dass die Verwendung in [Benutzermodellen in Skype for Business Server](user-models.md)zusammengefasst ist.

**Eigenständige Vermittlungs Server Kapazität: 70% interne Benutzer, 30% externe Benutzer mit nicht-Bypass-Anrufkapazität (vom Vermittlungsserver durchgeführte Medienumwandlung)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|**Maximale Anzahl von T1-Leitungen**|**Maximale Anzahl von E1-Leitungen**|
|:-----|:-----|:-----|:-----|
|Dualprozessor, Vierkern, Hyperthreading-CPU mit 2,26 GHz  **und deaktiviertem Hyperthreading **, 32 GB Arbeitsspeicher und einem Dualport-Netzwerkadapter.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Dualprozessor, Sechskern, Hyperthreading-CPU mit 2,26 GHz, 32 GB Arbeitsspeicher und ein Dualport-Netzwerkadapter.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Obwohl Server mit 32 GB Arbeitsspeicher für Leistungstests verwendet wurden, werden Server mit 16 GB Arbeitsspeicher für eigenständigen Vermittlungs Server unterstützt und genügen, um die in dieser Tabelle gezeigte Leistung bereitzustellen.

**Vermittlungsserver Kapazität (Mediationsserver mit Front-End-Server) 70% interne Benutzer, 30% externe Benutzer, nicht-Bypass-Anrufkapazität (Medienverarbeitung vom Vermittlungsserver ausgeführt)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|
|:-----|:-----|
|Dualprozessor, Sechskern, Hyperthreading-CPU mit 2,26 GHz und deaktiviertem Hyperthreading, 32 GB Arbeitsspeicher und zwei Netzwerkadapter mit 1 GB.  <br/> |150  <br/> |

> [!NOTE]
> Diese Zahl ist viel kleiner als die Zahlen für den eigenständigen Vermittlungs Server. Der Grund dafür ist, dass der Front-End-Server neben den für Sprachanrufe erforderlichen Transcodierungs Funktionen auch andere Features und Funktionen für die 6600-Benutzer verwaltet, die sich auf ihm befinden.

> [!NOTE]
> Um die Leistung des Vermittlungsservers zu verbessern, sollten Sie auf den Netzwerkadaptern auf Ihren Vermittlungsservern die Receive-Side-Skalierung (RSS) aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "[empfangsseitige Skalierung in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="back-end-server"></a>Back-End-Server

Obwohl viele Datenbankinformationen hauptsächlich auf den Front-End-Servern gespeichert werden, sollten Sie sicherstellen, dass Ihre Back-End-Server die Hardwareempfehlungen erfüllen, die weiter oben in diesem Abschnitt und auf [Server Hardwareplattformen](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)aufgeführt sind.

Zur Bereitstellung einer großen Verfügbarkeit Ihres Back-End-Servers empfehlen wir die Bereitstellung von AlwaysOn-Verfügbarkeitsgruppen oder Server Spiegelung. Weitere Informationen dazu finden Sie unter [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

Wenn Sie die Überwachung oder Archivierung bereitstellen, wird die Front-End-Funktionalität dieser Dienste auf den Front-End-Servern ausgeführt, wobei jede Verwendung Ihres eigenen Datenbankspeichers getrennt vom Back-End-Speicher verwendet wird. Wenn Sie jedoch Exchange 2013 bereitgestellt haben, können Sie Sofortnachrichten-Archivierungsdaten in Exchange anstatt in einem dedizierten SQL Store speichern.

Die folgende Tabelle zeigt, wie viele Datenbankspeicher pro Benutzer und Tag für die Daten aus der Überwachung und Archivierung in etwa benötigt wird.

||**KDS (Überwachung)** <br/> |**QoE (Überwachung)** <br/> |**Archiving** <br/> |
|:-----|:-----|:-----|:-----|
|Pro Benutzer und Tag benötigter Festplattenspeicher  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft hat bei den Leistungstests für den Datenbankserver die in der folgenden Tabelle aufgeführte Hardware für die Überwachung und Archivierung eingesetzt. Die Tests sammelten die Daten von zwei Front-End-Pools, die jeweils 80.000-Benutzer enthielten.

**Beim Leistungstest der Überwachung und Archivierung eingesetzte Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz  <br/> |
|Arbeitsspeicher  <br/> |48 GB  <br/> |
|Festplatte  <br/> |25 10.000-rpm-Festplattenlaufwerke mit 300 GB auf jeder Festplatte, mit der Konfiguration in der folgenden Tabelle  <br/> |
|Netzwerk  <br/> | 1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür die Verknüpfung mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist)  <br/> |

**Empfohlene Festplattenkonfigurationen**

|**Laufwerk** <br/> |**RAID-Konfiguration** <br/> |**Anzahl Festplatten** <br/> |
|:-----|:-----|:-----|
|KDS-, QoE- und Archivdatenbankdateien auf einem einzigen Laufwerk  <br/> |1+0  <br/> |16  <br/> |
|KDS-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|QoE-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|Archiv-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Video-Interop-Server Kapazität

Wenn Sie den Video-Interop-Server bereitstellen und die Kapazität ermitteln müssen, sehen Sie sich die maximale Anzahl von Video Teleconferencing-Systemen (VTCs) an, die sich in gleichzeitigen anrufen befinden. Wenn Sie zum Beispiel 250 Telekonferenzsysteme in Ihrem Unternehmen haben und wenn Ihr Benutzermodell die Schätzung ausweist, dass maximal 20 % davon gleichzeitig an Anrufen beteiligt sein werden, nehmen Sie 50 gleichzeitige Telefonkonferenzsysteme als Basis für Ihre Planung.


