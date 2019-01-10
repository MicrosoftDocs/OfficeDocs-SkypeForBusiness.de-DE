---
title: Verwendung des Objektmodells für Benutzer für Skype für Business Server zum Planen der Kapazität
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Dieser Artikel enthält Anleitungen für wie viele Server an einem Standort für die Anzahl von Benutzern an diesem Standort Sie müssen gemäß der Verwendung in Benutzermodelle in Skype for Business Server beschrieben.
ms.openlocfilehash: 1e802bc130086bcefc8fd06cbacd3f21222d6d0a
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789405"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Verwendung des Objektmodells für Benutzer für Skype für Business Server zum Planen der Kapazität

Dieser Artikel enthält Anleitungen für wie viele Server an einem Standort für die Anzahl von Benutzern an diesem Standort Sie müssen gemäß der Verwendung unter [User Models in Skype für Business Server](user-models.md)beschrieben.

> [!NOTE]
> Alle Empfehlungen in diesem Artikel gehen davon aus, dass Sie das kumulative Update für Skype for Business vom November 2015 oder ein jüngeres Update auf Ihren Servern installiert haben.

## <a name="tested-hardware-platform"></a>Getestete Hardwareplattform

Unsere Leistungstests wurden auf der in der Tabelle unten genannten Hardware durchgeführt. Alle unsere Empfehlungen und Ergebnisse beruhen auf dieser Hardware. Sofern Sie sich zur Verwendung einer weniger leistungsfähigen als der aufgeführten Hardware entschließen, seien Sie sich bewusst, dass unter Umständen Funktionalitätsprobleme oder Leistungseinbußen auftreten können. Diese hardwareempfehlungen sind identisch mit Lync Server 2013, wenn das hilfreich ist (und in Upgradeszenarien, kann es sein).

**Bei Leistungstests eingesetzte Hardware**

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz.  <br/> Intel Itanium-Prozessoren werden für Skype für Serverrollen Business Server nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |8 oder mehr Festplatten mit 10.000 U/Min mit mindestens 72 GB freiem Speicher. Zwei Festplatten sollten RAID 1 verwenden und sechs Festplatten sollten RAID 10 verwenden.  <br/> – ODER – <br/>Solid State-Laufwerke (SSDs), die Leistung wie 8 Festplattenlaufwerke mit 10.000 u / mechanische bereitstellen. <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür ein Teamvorgang mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist).  <br/> |

## <a name="summary-of-results"></a>Zusammenfassung der Ergebnisse

Eine Übersicht über unsere Empfehlungen finden Sie in der folgenden Tabelle.

|**Serverrolle**|**Maximale Anzahl von unterstützten Benutzern**|
|:-----|:-----|
|Front-End-Pool mit zwölf Front-End-Servern und eine Back-End-Server oder zwei gespiegelten Back-End-Servern.  <br/> |80.000 eindeutige Benutzer, plus 50 % Anmeldungen auf mehreren Geräten (Multiple Point Of Presence, MPOP), die keine mobilen Instanzen sind, plus 40 % Benutzer, die für Mobilität aktiviert sind, für insgesamt 152.000 Endpunkte.  <br/> |
|A/V-Konferenzen  <br/> |Der A / V-Konferenzdienst von einem Front-End-Pool bereitgestellten unterstützt die Konferenzen des Pools unter der Annahme einer maximalen konferenzgröße von 250 Benutzern und nur eine Konferenz dieser Größe zu einem Zeitpunkt ausgeführt.  <br/> **Hinweis:** Darüber hinaus können Sie große Konferenzen von 250 bis 1000 Benutzern durch die Bereitstellung eines separaten Front-End-Pools mit zwei Front-End-Server zum Hosten der großen Konferenzen unterstützen. Weitere Informationen hierzu finden Sie unter [Planen von großen Besprechungen in Skype für Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Ein Edge-Server  <br/> |12.000 Remotebenutzer gleichzeitig  <br/> |
|Ein Director  <br/> |12.000 Remotebenutzer gleichzeitig  <br/> |
|Überwachen und Archivieren  <br/> |Die Überwachung und Archivierung Front-End-Dienste auf jedem Front-End-Server, anstatt in separaten Serverrollen ausgeführt.  <br/> Für das Überwachen und Archivieren sind weiterhin eigene Datenbankspeicher erforderlich. Wenn Sie auch Exchange 2013 ausführen oder höher, Sie Ihre Archivierungsdaten, Exchange, statt in einer dedizierten SQL-Datenbank beibehalten können.  <br/> |
|Ein Vermittlungsserver  <br/> |Vermittlungsserver mit dem Front-End-Server ausgeführt wird, klicken Sie auf jedem Front-End-Server in einem Pool verbunden und sollte über ausreichend Kapazität für die Benutzer im Pool bereitstellen. Finden Sie für eigenständige Vermittlungsserver im Abschnitt "Vermittlungsserver" weiter unten in diesem Thema.  <br/> |
|Ein Standard Edition-server  <br/> |Es wird dringend empfohlen, bei Verwendung von Standard Edition-Servern, Benutzern Host immer zwei Server, kombiniert mit den Empfehlungen in [Planning for High Availability and Disaster Recovery](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx)verwenden. Jeder Server der Kombination kann bis zu 2.500 Benutzer hosten und wenn ein Server ausfällt, kann der verbleibende Server in einem Failoverszenario 5.000 Benutzer unterstützen.  <br/>  Wenn in Ihrer Bereitstellung Audio- oder Videodatenverkehr im großen Umfang anfällt, wird die Serverleistung u. U. auch bei mehr als 2.500 Benutzern pro Server beeinträchtigt. In diesem Fall sollten Sie erwägen, Hinzufügen weiterer Standard Edition-Server oder das Verschieben in Skype für Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Front-End-Server

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

In einem Front-End-Pool sollte ein Front-End-Server für jede 6.660 Benutzern in Ihrem Pool verwaltet werden, unter der Annahme, dass auf allen Servern im Pool und, Hyperthreading aktiviert ist erfüllt die Serverhardware die Empfehlungen in [Server-Anforderungen für Skype für Business Server 2015](../requirements-for-your-environment/server-requirements.md) oder [Systemanforderungen für Skype für Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 80.000, erneut ein, unter der Annahme, dass auf allen Servern im Pool Hyperthreading aktiviert ist. Wenn Sie mehr als 80.000 Benutzern an einem Standort verfügen, können Sie mehrere Front-End-Pool bereitstellen.

Wenn Sie berücksichtigen, für die Anzahl der Benutzer in einem Front-End-Pool, enthalten keine Benutzer verwaltet auf Survivable Branch Appliances und Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool zugeordnet sind.

Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen. In einem Szenario, in denen Sie über 30.000 Benutzer und fünf Front-End-Server, wenn ein Server nicht verfügbar ist, müssen die Verbindungen des 6000 Ihrer Benutzer auf den anderen vier verbleibenden Servern übertragen werden. Auf den übrigen vier Servern würden in diesem Fall je 7.500 Benutzer verwaltet, sodass die empfohlene Anzahl überschritten wäre.

Wenn Sie hatte stattdessen mit sechs Front-End-Servern gestartet, für die 30.000 Benutzer und eine nicht mehr verfügbar ist, müssen insgesamt 5000 Benutzer in den verbleibenden fünf Servern zu verschieben. Diese fünf Server hosten dann jeweils 6.000 Benutzer, was im empfohlenen Bereich liegt.

Die maximale Anzahl von Benutzern in einem Front-End-Pool ist 80.000. Die maximale Anzahl von Front-End-Servern in einem Pool lautet 12.

Für einen Front-End-Pool mit 80.000 Benutzern werden zwölf Front-End-Servern für die Leistung im normalen Bereitstellungen, die die [Benutzermodelle in Skype für Business Server](user-models.md)folgen. Bereitstellungen Disaster Recovery Failover unterstützt wird davon ausgegangen, dass ein Maximum von 40.000 Benutzer in den einzelnen zwei gekoppelten Front-End-Pools gehostet werden kann, in dem jeder Pool ausreichend Front-End-Server enthält die Benutzer in beiden Pools hat einen Pool Failover t ausgeführt werden müssen o der anderen.

Die Anzahl der Benutzer mit einer guten Leistung durch einen bestimmten Front-End-Pool unterstützt kann von dieser Zahlen aus den folgenden Gründen abweichen:

- Die Hardware für die Front-End-Server erfüllen nicht die Empfehlungen.

- Der Verwendungsoptionen unterscheidet sich aus den Benutzermodellen, beispielsweise wenn Sie viel mehr Webkonferenz-Datenverkehr verfügen.

Die folgende Tabelle zeigt die durchschnittliche Bandbreite für SOFORTNACHRICHTEN- und Anwesenheitsdaten basierend auf das Benutzermodell, unter [User Models in Skype für Business Server](user-models.md)definiert sind.

|**Durchschnittliche Bandbreite pro Benutzer**|**Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern**|
|:-----|:-----|
|1,3 KBit/s  <br/> |13 MBit/s  <br/> |

> [!NOTE]
> Zum Verbessern der Leistung Media am selben Standort A / V-Konferenzen und Vermittlungsserver Funktionalität auf Front-End-Servern, aktivieren Sie erhalten-Side Skalierung (RSS) auf die Netzwerkadapter auf Front-End-Servern. RSS ermöglicht die parallele Bearbeitung eingehender Pakete durch mehrere Prozessoren auf dem Server. Ausführliche Informationen dazu finden Sie unter [„Empfangsseitige Skalierung (RSS)“ in der Dokumentation von Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="conferencing-maximums"></a>Maximale Anzahl von Benutzern für Konferenzen

Bei einem Benutzermodell, bei dem 5 % der Benutzer in einem Pool gleichzeitig an einer Konferenz teilnehmen können, können in einem Pool mit 80.000 Benutzern gleichzeitig ca. 4.000 Benutzer an einer Konferenz teilnehmen. Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z. B. nur Chatnachrichten, Chatnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt. Es gibt keine harte Grenze für die tatsächliche Anzahl von zulässigen Konferenzen, die tatsächliche Leistung ist durch die tatsächliche Nutzung bestimmt. Angenommen, wenn Ihre Organisation viele weitere gemischten Modus Konferenzen als im Benutzermodell wird angenommen, dass verfügt, Sie müssen möglicherweise mehrere Front-End-Server oder eine Bereitstellung von / V-Konferenzserver als die Empfehlungen in diesem Artikel gefunden. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in Skype für Business Server beschrieben](user-models.md).

Die maximale unterstützte konferenzgröße von einem regulären Skype für Business Server-Front-End-Pool der auch als Host für Benutzer fungiert gehostet ist 250 Teilnehmer. Während eine Konferenz 250 Benutzer Ball, unterstützt den Pool noch andere Konferenzen sowie, so, dass insgesamt 5 % der Pool-Benutzer befinden sich in gleichzeitige Konferenzen. Während die Konferenz 250 Benutzer Ball, unterstützt beispielsweise in einem Pool mit zwölf Front-End-Servern und 80.000 Benutzern, Skype für Business Server 3,750 anderen Benutzern in kleinere Konferenzen teilnehmen.

Unabhängig von der Anzahl der Benutzer, die sich in den Front-End-Pool oder Skype für Business Server Standard Edition-Server unterstützt mindestens 125 anderer Benutzer in demselben Pool oder auf dem Server, die eine Konferenz 250 Benutzer hostet, ist kleiner Konferenzen teilnehmen.

Zum Aktivieren von Konferenzen, die zwischen 250 und 1000 Benutzern haben, können Sie einen separaten Front-End-Pool einrichten, um diese Konferenzen gehostet. Alle Benutzer werden nicht von diesem Front-End-Pool gehostet werden. Weitere Informationen hierzu finden Sie in der [von großen Besprechungen in Skype für Business Server planen](../../plan-your-deployment/conferencing/large-meetings.md).

Wenn Ihre Organisation eine Vielzahl weiterer gemischten Modus Konferenzen als im Benutzermodell wird angenommen, dass verfügt, müssen Sie möglicherweise mehrere Front-End-Server als wir Empfehlung in diesem Dokument (bis zu einem Maximum von 12 Front-End-Servern) bereitstellen. Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in Skype für Business Server beschrieben](user-models.md).

## <a name="edge-server"></a>Edgeserver

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Sie sollten für jede 12.000 Remotebenutzer eine Edge-Server bereitstellen, die auf eine Website gleichzeitig zugreifen. Mindestens empfehlen wir zwei Edge-Server für hohe Verfügbarkeit. Diese Empfehlungen wird davon ausgegangen, dass die Hardware für Edge-Server die Empfehlungen in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)erfüllt.

Wenn Sie für die Anzahl der Benutzer für den Edge-Servern, auch die Benutzer Konto verwaltet auf Survivable Branch Appliances und Survivable Branch Servern in Zweigstellen, die einem Front-End-Pool an diesem Standort zugeordnet sind.

> [!NOTE]
> Zur Verbesserung der Leistung des A / V Conferencing-edgedienst auf den Edge-Servern sollten Sie empfangen der clientseitigen Skalierung (RSS) auf den Netzwerkadaptern auf Edge-Servern aktivieren. RSS ermöglicht die parallele Bearbeitung eingehender Pakete durch mehrere Prozessoren auf dem Server. Details finden Sie in "[Empfangen Seite Skalierung (RSS) in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="director"></a>Director

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie den Director-Server-Role bereitstellen, wird empfohlen, dass Sie einen Director für jede 12.000 Remotebenutzer bereitstellen, die auf eine Website gleichzeitig zugreifen. Mindestens empfehlen wir zwei Directors für hohe Verfügbarkeit. Diese Empfehlungen wird davon ausgegangen, dass die Hardware für Edge-Server die Empfehlungen in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)erfüllt.

Wenn Sie für die Anzahl der Benutzer für die Directors auch die Benutzer Konto verwaltet auf Survivable Branch Appliances und Survivable Branch Servern in Zweigstellen, die einem Front-End-Pool an diesem Standort zugeordnet sind.

## <a name="mediation-server"></a>Vermittlungsserver

> [!NOTE]
> Erweiterte Pools werden für diese Serverrolle nicht unterstützt.

Wenn Sie Vermittlungsserver mit Front-End-Server zusammenstellen, Vermittlungsserver wird auf jedem Front-End-Server im Pool ausgeführt und sollte über ausreichend Kapazität für die Benutzer im Pool bereitstellen.

Wenn Sie einen eigenständigen vermittlungsserverpool, und klicken Sie dann auf wie viele Vermittlungsserver bereitstellen zum Bereitstellen von hängt von vielen Faktoren ab, einschließlich der für den Vermittlungsserver, die Anzahl der VoIP-Benutzern stehen Ihnen verwendeten Hardware, die Anzahl der Gateway peers, die jede vermittlungsserverpool Steuerelemente, Datenverkehr zu Spitzenzeiten über diese Gateways verarbeitet wird, und den Prozentsatz der Anrufe mit Medien, die den Vermittlungsserver umgeht.

Die folgenden Tabellen enthalten eine Richtlinie für wie viele gleichzeitige Aufrufe einen Vermittlungsserver verarbeitet werden können, unter der Annahme, dass die Hardware für die Vermittlungsserver die Anforderungen in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) erfüllt und dass Hyperthreading aktiviert ist. Ausführliche Informationen zur Skalierbarkeit von Vermittlungsservern finden Sie unter [Estimating Voice-Nutzung und-Datenverkehr für Skype für Business Server](estimating-voice-traffic.md) und [Bereitstellungsrichtlinien für den Vermittlungsserver in Skype für Business Server](mediation-server-deployment-guidelines.md).

Alle in den folgenden Tabellen gehen von einer Verwendung unter [User Models in Skype für Business Server](user-models.md)zusammengefasst.

**Kapazität eigenständiger Vermittlungsserver: 70 % interne Benutzer, ohne Umgehung 30 % externe Benutzer mit Anruf Kapazität (medientranscodierung durch Mediation Server)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|**Maximale Anzahl von T1-Leitungen**|**Maximale Anzahl von E1-Leitungen**|
|:-----|:-----|:-----|:-----|
|Dualprozessor, Vierkern, Hyperthreading-CPU mit 2,26 GHz  **und deaktiviertem Hyperthreading **, 32 GB Arbeitsspeicher und einem Dualport-Netzwerkadapter.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Dualprozessor, Sechskern, Hyperthreading-CPU mit 2,26 GHz, 32 GB Arbeitsspeicher und ein Dualport-Netzwerkadapter.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Obwohl Server mit 32 GB Arbeitsspeicher für Leistungstests verwendet wurden, Server mit 16 GB Arbeitsspeicher für eigenständige Vermittlungsserver unterstützt werden und sind ausreichend, um die Leistung in dieser Tabelle aufgeführten bereitstellen.

**Kapazität Vermittlungsserver (Vermittlungsserver kombiniert mit Front-End-Server) 70 % interne Benutzer, 30 % externe Benutzer, keine Umgehung Anruf Kapazität (Medienverarbeitung durch Mediation Server ausgeführt)**

|**Serverhardware**|**Maximale Anzahl von Anrufen**|
|:-----|:-----|
|Dualprozessor, Sechskern, Hyperthreading-CPU mit 2,26 GHz und deaktiviertem Hyperthreading, 32 GB Arbeitsspeicher und zwei Netzwerkadapter mit 1 GB.  <br/> |150  <br/> |

> [!NOTE]
> Diese Nummer wird viel kleiner als die Zahlen für den eigenständigen Vermittlungsserver. Dies liegt daran der Front-End-Server muss verarbeiten andere Features und Funktionen für die 6600 Benutzer verwaltet, zusätzlich zu der Transcodierungsvorgabe für Sprachanrufe erforderlich ist.

> [!NOTE]
> Zum Verbessern der Leistung des Vermittlungsservers, sollten Sie empfangen der clientseitigen Skalierung (RSS) auf die Netzwerkadapter auf Ihrem Vermittlungsservern aktivieren. RSS ermöglicht die parallele Bearbeitung eingehender Pakete durch mehrere Prozessoren auf dem Server. Weitere Informationen hierzu finden Sie unter "[Receive-Side Scaling in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.

## <a name="back-end-server"></a>Back-End-Server

Obwohl ein Großteil der Datenbankinformationen in erster Linie auf den Front-End-Servern gespeichert werden, sollten Sie sicherstellen, dass die Back-End-Server weiter oben in diesem Abschnitt und in [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)aufgeführten hardwareempfehlungen erfüllen.

Es wird empfohlen, um hohe Verfügbarkeit der Back-End-Server zu ermöglichen, AlwaysOn Availability Groups oder Server-Spiegelung bereitzustellen. Weitere Informationen dazu finden Sie unter [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

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
|CPU  <br/> |64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz  <br/> |
|Arbeitsspeicher  <br/> |48 GB  <br/> |
|Festplatte  <br/> |25 10.000 u / Festplatten mit 300 GB auf jedem Datenträger, mit der Konfiguration in der folgenden Tabelle  <br/> |
|Netzwerk  <br/> | 1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür die Verknüpfung mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist)  <br/> |

**Empfohlene Konfigurationen**

|**Laufwerk** <br/> |**RAID-Konfiguration** <br/> |**Anzahl Festplatten** <br/> |
|:-----|:-----|:-----|
|KDS-, QoE- und Archivdatenbankdateien auf einem einzigen Laufwerk  <br/> |1+0  <br/> |16  <br/> |
|KDS-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|QoE-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |
|Archiv-Datenbankprotokolldatei  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Video Interop-Server-Kapazität

Wenn Sie das Video Interop-Server bereitstellen, und Sie zum Ermitteln der Kapazität müssen, betrachten Sie die maximale Anzahl von Video Telekonferenzen Systeme (VTCs), die in gleichzeitige Anrufe werden. Wenn Sie zum Beispiel 250 Telekonferenzsysteme in Ihrem Unternehmen haben und wenn Ihr Benutzermodell die Schätzung ausweist, dass maximal 20 % davon gleichzeitig an Anrufen beteiligt sein werden, nehmen Sie 50 gleichzeitige Telefonkonferenzsysteme als Basis für Ihre Planung.


