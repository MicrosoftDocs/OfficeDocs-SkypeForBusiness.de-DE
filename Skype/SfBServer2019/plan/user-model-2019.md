---
title: Kapazitätsplanung für Skype für Business Server 2019
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Die Themen in diesem Abschnitt können Sie verstehen, wie Sie zum Planen und Bereitstellen von Skype für Business Server, sodass ausreichend planen zu können, für die Anzahl der Benutzer in Ihrer Organisation und Plan für die Auslastung des Servers, die deren Aktivitäten generieren.
ms.openlocfilehash: 996fd1df51442bcaadbd0ae548e9cf57e580279a
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696345"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Capacity Planning for Skype für Business Server 2019

Dieser Artikel enthält Anleitungen für wie viele Server Sie an einem Standort für die Anzahl von Benutzern an diesem Standort benötigen gemäß den unter [User Models in Skype für Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md) beschriebenen Verwendungsmöglichkeiten

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Unsere Leistungstests wurden auf der in der Tabelle unten genannten Hardware durchgeführt. Alle unsere Empfehlungen und Ergebnisse beruhen auf dieser Hardware. Sofern Sie sich zur Verwendung einer weniger leistungsfähigen als der aufgeführten Hardware entschließen, seien Sie sich bewusst, dass unter Umständen Funktionalitätsprobleme oder Leistungseinbußen auftreten können.

**Bei Leistungstests eingesetzte Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3-Dualprozessor, 6-Core mit 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype für Business Server 2019 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualmodus oder Multihoming-Konfigurationen werden **nicht** für Front-End-Server, Back-End-Servern und Standard Edition Server unterstützt. <br/> Solange sie nicht verfügbar, für das Betriebssystem gemacht sind und zu überwachen und Verwalten von Serverhardware verwendet werden, können Sie Out-of-Band-Management-Systemen, wie DRAC oder ILO haben. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.  <br/> |

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

Eine Übersicht über unsere Empfehlungen finden Sie in der folgenden Tabelle.

|**Serverrolle**|**Maximale Anzahl von unterstützten Benutzern**|
|:-----|:-----|
|Front-End-Pool mit sechzehn Front-End-Server und Back-End-Server oder ein Paar von Back-End-Servern mit SQL immer auf für hohe Verfügbarkeit.  <br/> |106.000 eindeutige angemeldeten Benutzer gleichzeitig, plus 50 % MPOP (MPOP), die nicht mobilen Instanzen sind, plus 40 % der Benutzer, die für Mobilität aktiviert sind, für insgesamt 210.000 Endpunkte darstellt.  <br/> |
|A/V-Konferenzen  <br/> |Der A / V-Konferenzdienst von einem Front-End-Pool bereitgestellten unterstützt die Konferenzen des Pools unter der Annahme einer maximalen konferenzgröße von 250 Benutzern und nur eine Konferenz dieser Größe zu einem Zeitpunkt ausgeführt.  <br/> **Hinweis:** Darüber hinaus können Sie große Konferenzen von 250 bis 1000 Benutzern durch die Bereitstellung eines separaten Front-End-Pools mit zwei Front-End-Server zum Hosten der großen Konferenzen unterstützen. Weitere Informationen hierzu finden Sie unter [Planen von großen Besprechungen in Skype für Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Ein Edge-Server  <br/> |18.000 gleichzeitige Remotebenutzer.  <br/> |
|Ein Director  <br/> |18.000 gleichzeitige Remotebenutzer.  <br/> |
|Überwachen und Archivieren  <br/> |Die Überwachung und Archivierung Front-End-Dienste auf jedem Front-End-Server, anstatt in separaten Serverrollen ausgeführt.  <br/> Für das Überwachen und Archivieren sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 ausführen oder höher, Sie Ihre Archivierungsdaten, Exchange, statt in einer dedizierten SQL-Datenbank beibehalten können.  <br/> |
|Ein Vermittlungsserver  <br/> |Vermittlungsserver mit dem Front-End-Server ausgeführt wird, klicken Sie auf jedem Front-End-Server in einem Pool verbunden und sollte über ausreichend Kapazität für die Benutzer im Pool bereitstellen. Finden Sie für eigenständige Vermittlungsserver im Abschnitt "Vermittlungsserver" weiter unten in diesem Thema.  <br/> |
|Ein Standard Edition-server  <br/> |Es wird dringend empfohlen, bei Verwendung von Standard Edition-Servern, Benutzern Host immer zwei Server, kombiniert mit den Empfehlungen in [Planning for High Availability and Disaster Recovery](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx)verwenden. Jeder Server der Kombination kann bis zu 2.500 Benutzer hosten und wenn ein Server ausfällt, kann der verbleibende Server in einem Failoverszenario 5.000 Benutzer unterstützen.  <br/>  Wenn in Ihrer Bereitstellung Audio- oder Videodatenverkehr im großen Umfang anfällt, wird die Serverleistung u. U. auch bei mehr als 2.500 Benutzern pro Server beeinträchtigt. In diesem Fall sollten Sie erwägen, Hinzufügen weiterer Standard Edition-Server oder das Verschieben in Skype für Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Front-End-Server

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

In einem Front-End-Pool sollte ein Front-End-Server für jede 6.660 Benutzern in Ihrem Pool verwaltet werden, sofern die hyper-threading auf allen Servern im Pool aktiviert ist, dass Sie SQL Server Express Edition und, verwenden die Serverhardware erfüllt der Empfehlungen in [Server-Anforderungen für Skype für Business Server 2019](system-requirements.md). Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 106,000, erneut ein, unter der Annahme, dass Hyperthreading aktiviert und SQL Server Express Edition auf allen Servern im Pool verwendet wird. Wenn Sie mehr als 106.000 Benutzer an einem Standort verfügen, können Sie mehrere Front-End-Pool bereitstellen.

Wenn Sie berücksichtigen, für die Anzahl der Benutzer in einem Front-End-Pool, enthalten keine Benutzer verwaltet auf Survivable Branch Appliances und Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. In einem Szenario, in denen Sie über 30.000 Benutzer und fünf Front-End-Server, wenn ein Server nicht verfügbar ist, müssen die Verbindungen des 6000 Ihrer Benutzer auf den anderen vier verbleibenden Servern übertragen werden. Auf den übrigen vier Servern würden in diesem Fall je 7.500 Benutzer verwaltet, sodass die empfohlene Anzahl überschritten wäre.

Wenn Sie hatte stattdessen mit sechs Front-End-Servern gestartet, für die 30.000 Benutzer und eine nicht mehr verfügbar ist, müssen insgesamt 5000 Benutzer in den verbleibenden fünf Servern zu verschieben. Diese fünf Server hosten dann jeweils 6.000 Benutzer, was im empfohlenen Bereich liegt.

Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 106,000. Die maximale Anzahl von Front-End-Servern in einem Pool, beträgt 16.

Für einen Front-End-Pool mit 80.000 Benutzern werden 16 Front-End-Servern für die Leistung im normalen Bereitstellungen, die die [Benutzermodelle in Skype für Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)folgen. Bereitstellungen Disaster Recovery Failover unterstützt wird davon ausgegangen, dass ein Maximum von 53.000 Benutzer in den einzelnen zwei gekoppelten Front-End-Pools gehostet werden kann, in dem jeder Pool ausreichend Front-End-Server enthält die Benutzer in beiden Pools hat einen Pool Failover t ausgeführt werden müssen o der anderen.

Die Anzahl der Benutzer mit einer guten Leistung durch einen bestimmten Front-End-Pool unterstützt kann von dieser Zahlen aus den folgenden Gründen abweichen:

- Die Hardware für die Front-End-Server erfüllen nicht die Empfehlungen.
- Anstelle von SQL Server Express Edition verwenden, verwenden Sie einen anderen SQL Server-Edition, möglicherweise zusätzliche Host-Benutzern in jedem Front-End-Pool können.
- Der Verwendungsoptionen unterscheidet sich aus den Benutzermodellen, beispielsweise wenn Sie viel mehr Webkonferenz-Datenverkehr verfügen.

Die folgende Tabelle zeigt die durchschnittliche Bandbreite für SOFORTNACHRICHTEN- und Anwesenheitsdaten basierend auf das Benutzermodell, unter [User Models in Skype für Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)definiert sind.

|**Durchschnittliche Bandbreite pro Benutzer**|**Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern**|
|:-----|:-----|
|3-3,75 Kbit/s  <br/> |13 Mbit/s  <br/> |

> [!NOTE]
> Zum Verbessern der Leistung Media am selben Standort A / V-Konferenzen und Vermittlungsserver Funktionalität auf Front-End-Servern, aktivieren Sie erhalten-Side Skalierung (RSS) auf die Netzwerkadapter auf Front-End-Servern. RSS ermöglicht die parallele Bearbeitung eingehender Pakete durch mehrere Prozessoren auf dem Server. Ausführliche Informationen dazu finden Sie unter [„Empfangsseitige Skalierung (RSS)“ in der Dokumentation von Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Basierend auf das Benutzermodell, das jeweils 5 % der Benutzer in einem Pool in einer Konferenz sein können, konnte ein Pool von 106.000 Benutzer etwa 5.300 Benutzer haben in Konferenzen gleichzeitig. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z. B. nur Chatnachrichten, Chatnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl von zulässigen Konferenzen, die tatsächliche Leistung ist durch die tatsächliche Nutzung bestimmt. Angenommen, wenn Ihre Organisation viele weitere gemischten Modus Konferenzen als im Benutzermodell wird angenommen, dass verfügt, Sie müssen möglicherweise mehrere Front-End-Server oder eine Bereitstellung von / V-Konferenzserver als die Empfehlungen in diesem Artikel gefunden. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in Skype für Business Server beschrieben](../../SfbServer/plan-your-deployment/capacity/user-models.md).

Die maximale unterstützte konferenzgröße von einem regulären Skype für Business Server-Front-End-Pool der auch als Host für Benutzer fungiert gehostet ist 250 Teilnehmer. Während eine Konferenz 250 Benutzer Ball, unterstützt den Pool noch andere Konferenzen sowie, so, dass insgesamt 5 % der Pool-Benutzer befinden sich in gleichzeitige Konferenzen. Während die Konferenz 250 Benutzer Ball, unterstützt beispielsweise in einem Pool von 16 Front-End-Servern und 106.000 Benutzern, Skype für Business Server 5,050 anderen Benutzern in kleinere Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die sich in den Front-End-Pool oder Skype für Business Server Standard Edition-Server unterstützt mindestens 125 anderer Benutzer in demselben Pool oder auf dem Server, die eine Konferenz 250 Benutzer hostet, ist kleiner Konferenzen teilnehmen.

Zum Aktivieren von Konferenzen, die zwischen 250 und 1000 Benutzern haben, können Sie einen separaten Front-End-Pool einrichten, um diese Konferenzen gehostet. Alle Benutzer werden nicht von diesem Front-End-Pool gehostet werden. Weitere Informationen hierzu finden Sie in der [von großen Besprechungen in Skype für Business Server planen](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md).

Wenn Ihre Organisation eine Vielzahl weiterer gemischten Modus Konferenzen als im Benutzermodell wird angenommen, dass verfügt, müssen Sie möglicherweise mehrere Front-End-Server als wir Empfehlung in diesem Dokument (bis zu einem Maximum von 16 Front-End-Servern) bereitstellen. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in Skype für Business Server beschrieben](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>Edgeserver

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Sie sollten für jede 18.000 Remotebenutzer eine Edge-Server bereitstellen, die auf eine Website gleichzeitig zugreifen. Mindestens empfehlen wir zwei Edge-Server für hohe Verfügbarkeit. Diese Empfehlungen wird davon ausgegangen, dass die Hardware für Edge-Server die Empfehlungen in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)erfüllt.

Wenn Sie für die Anzahl der Benutzer für den Edge-Servern, auch die Benutzer Konto verwaltet auf Survivable Branch Appliances und Survivable Branch Servern in Zweigstellen, die einem Front-End-Pool an diesem Standort zugeordnet sind.

> [!NOTE]
> Zur Verbesserung der Leistung des A / V Conferencing-edgedienst auf den Edge-Servern sollten Sie empfangen der clientseitigen Skalierung (RSS) auf den Netzwerkadaptern auf Edge-Servern aktivieren. RSS ermöglicht die parallele Bearbeitung eingehender Pakete durch mehrere Prozessoren auf dem Server. Überprüfen Sie weitere Informationen hierzu [Erhalten Seite Skalierung (RSS) in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="director"></a>Director

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie den Director-Server-Role bereitstellen, wird empfohlen, dass Sie einen Director für jede 18.000 Remotebenutzer bereitstellen, die auf eine Website gleichzeitig zugreifen. Mindestens empfehlen wir zwei Directors für hohe Verfügbarkeit. Diese Empfehlungen wird davon ausgegangen, dass die Hardware für Edge-Server die Empfehlungen in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)erfüllt.

Wenn Sie für die Anzahl der Benutzer für die Directors auch die Benutzer Konto verwaltet auf Survivable Branch Appliances und Survivable Branch Servern in Zweigstellen, die einem Front-End-Pool an diesem Standort zugeordnet sind.

## <a name="mediation-server"></a>Vermittlungsserver

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie Vermittlungsserver mit Front-End-Server zusammenstellen, Vermittlungsserver wird auf jedem Front-End-Server im Pool ausgeführt und sollte über ausreichend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen vermittlungsserverpool, und klicken Sie dann auf wie viele Vermittlungsserver bereitstellen zum Bereitstellen von hängt von vielen Faktoren ab, einschließlich der für den Vermittlungsserver, die Anzahl der VoIP-Benutzern stehen Ihnen verwendeten Hardware, die Anzahl der Gateway peers, die jede vermittlungsserverpool Steuerelemente, Datenverkehr zu Spitzenzeiten über diese Gateways verarbeitet wird, und den Prozentsatz der Anrufe mit Medien, die den Vermittlungsserver umgeht.

Die folgenden Tabellen enthalten eine Richtlinie für wie viele gleichzeitige Aufrufe einen Vermittlungsserver verarbeitet werden können, unter der Annahme, dass die Hardware für die Vermittlungsserver die Anforderungen in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) erfüllt und dass Hyperthreading aktiviert ist. Ausführliche Informationen zur Skalierbarkeit von Vermittlungsservern finden Sie unter [Estimating Voice-Nutzung und-Datenverkehr für Skype für Business Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) und [Bereitstellungsrichtlinien für den Vermittlungsserver in Skype für Business Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Alle in den folgenden Tabellen gehen von einer Verwendung unter [User Models in Skype für Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)zusammengefasst.

**Kapazität eigenständiger Vermittlungsserver: 70 % interne Benutzer, ohne Umgehung 30 % externe Benutzer mit Anruf Kapazität (medientranscodierung durch Mediation Server)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|**Maximale Anzahl von T1-Leitungen**|**Maximale Anzahl von E1-Leitungen**|
|:-----|:-----|:-----|:-----|
|Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 Gigahertz (GHz) oder höher **mit Hyperthreading deaktiviert**, mit 64 GB Arbeitsspeicher und einem DualPort-Netzwerkadapter.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel Xeon E5-2673 v3-Dualprozessor, 6-Core mit 2,4 Gigahertz (GHz) oder höher, mit 64 GB Arbeitsspeicher und einem DualPort-Netzwerkadapter.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Obwohl Server mit 64 GB Speicher für Leistungstests verwendet wurden, Server mit 32 GB Arbeitsspeicher für eigenständige Vermittlungsserver unterstützt werden und sind ausreichend, um die Leistung in dieser Tabelle aufgeführten bereitstellen.

**Kapazität Vermittlungsserver (Vermittlungsserver kombiniert mit Front-End-Server) 70 % interne Benutzer, 30 % externe Benutzer, keine Umgehung Anruf Kapazität (Medienverarbeitung durch Mediation Server ausgeführt)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|
|:-----|:-----|
|Intel Xeon E5-2673 v3-Dualprozessor, 6-Core mit 2,4 Gigahertz (GHz) oder höher. mit 64 GB Arbeitsspeicher und 2 Netzwerkkarten von 1GB.  <br/> |200  <br/> |

> [!NOTE]
> Diese Nummer wird viel kleiner als die Zahlen für den eigenständigen Vermittlungsserver. Dies liegt daran der Front-End-Server muss verarbeiten andere Features und Funktionen für die 6600 Benutzer verwaltet, zusätzlich zu der Transcodierungsvorgabe für Sprachanrufe erforderlich ist.

> [!NOTE]
> Zum Verbessern der Leistung des Vermittlungsservers, sollten Sie empfangen der clientseitigen Skalierung (RSS) auf die Netzwerkadapter auf Ihrem Vermittlungsservern aktivieren. RSS ermöglicht die parallele Bearbeitung eingehender Pakete durch mehrere Prozessoren auf dem Server. Weitere Informationen hierzu finden Sie unter "[Receive-Side Scaling in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="back-end-server"></a>Back-End-Server

Obwohl ein Großteil der Datenbankinformationen in erster Linie auf den Front-End-Servern gespeichert werden, sollten Sie sicherstellen, dass die Back-End-Server weiter oben in diesem Abschnitt und in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)aufgeführten hardwareempfehlungen erfüllen.

Es wird empfohlen, um hohe Verfügbarkeit der Back-End-Server zu ermöglichen, AlwaysOn Availability Groups oder Server-Spiegelung bereitzustellen. Weitere Informationen dazu finden Sie unter [Back End Server high availability in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

Wenn Sie die Überwachung und den Archivierungsserver bereitstellen, die Front-End-Funktionalität dieser Dienste auf den Front-End-Servern ausgeführt wird, Überwachung und Archivierung eigene Datenbankspeicher getrennt von den Back-End-Speicher verwenden. Auch wenn Sie Exchange 2013 bereitgestellt haben, können Sie Sofortnachrichtendaten archivieren im Exchange anstatt in einem dedizierten SQL-Speicher speichern.

Die folgende Tabelle zeigt, wie viele Datenbankspeicher pro Benutzer und Tag für die Daten aus der Überwachung und Archivierung in etwa benötigt wird.

||**KDS (Überwachung)** <br/> |**QoE (Überwachung)** <br/> |**Archiving** <br/> |
|:-----|:-----|:-----|:-----|
|Pro Benutzer und Tag benötigter Festplattenspeicher  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft hat bei den Leistungstests für den Datenbankserver die in der folgenden Tabelle aufgeführte Hardware für die Überwachung und Archivierung eingesetzt. Für die Tests erfasst die Daten von zwei Front-End-Pools, von die jedes 80.000 Benutzern enthalten.

**Beim Leistungstest der Überwachung und Archivierung eingesetzte Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3-Dualprozessor, 6-Core mit 2,4 Gigahertz (GHz) oder höher.  <br/> |
|Arbeitsspeicher  <br/> |48 GB  <br/> |
|Festplatte  <br/> |
ENTWEDER: • 4 oder weitere 10.000 u/Min. Festplatten mit mindestens 72 GB freiem Speicherplatz (Festplatten sollte in eine 2 x RAID 1-Konfiguration). ODER • Solid State-Laufwerke (SSDs) liefern die gleichen freiem Speicherplatz und ähnliche Leistung 4 Festplattenlaufwerke mit 10.000 u/Min. mechanische.   <br/> | | Netzwerk  <br/> | 1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 empfohlen, der ein teaming mit einer einzelnen MAC-Adresse und einzelne IP-Adresse erfordert).  <br/> |

**Empfohlene Konfigurationen**

|**Laufwerk** <br/> |**RAID-Konfiguration** <br/> |**Anzahl Festplatten** <br/> |
|:-----|:-----|:-----|
|KDS-, QoE- und Archivdatenbankdateien auf einem einzigen Laufwerk  <br/> |1+0  <br/> |16  <br/> |
|KDS-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|QoE-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|Archiv-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Video Interop-Server-Kapazität

Wenn Sie das Video Interop-Server bereitstellen, und Sie zum Ermitteln der Kapazität müssen, betrachten Sie die maximale Anzahl von Video Telekonferenzen Systeme (VTCs), die in gleichzeitige Anrufe werden. Wenn Sie zum Beispiel 250 Telekonferenzsysteme in Ihrem Unternehmen haben und wenn Ihr Benutzermodell die Schätzung ausweist, dass maximal 20 % davon gleichzeitig an Anrufen beteiligt sein werden, nehmen Sie 50 gleichzeitige Telefonkonferenzsysteme als Basis für Ihre Planung.

