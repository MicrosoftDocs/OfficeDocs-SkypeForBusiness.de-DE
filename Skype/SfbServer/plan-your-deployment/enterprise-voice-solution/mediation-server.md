---
title: Vermittlungsserverkomponente in Skype for Business Server
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
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Erfahren Sie mehr über Vermittlungsserver in Skype for Business Server, einschließlich der unterstützten Topologien und ihrer Beziehungen zu M:N-Trunks, Medienumgehung und Anrufsteuerung.
ms.openlocfilehash: ef95e03bb9cc604b50e0e417f8358f6d922a7819
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101351"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Vermittlungsserverkomponente in Skype for Business Server
 
Erfahren Sie mehr über Vermittlungsserver in Skype for Business Server, einschließlich der unterstützten Topologien und ihrer Beziehungen zu M:N-Trunks, Medienumgehung und Anrufsteuerung.
  
Zum Bereitstellen Enterprise-VoIP müssen Sie einen oder mehrere Vermittlungsserver bereitstellen. 
  
Der Vermittlungsserver übersetzt Die Signalisierung zwischen Ihrer internen Enterprise-VoIP-Infrastruktur und einem PstN-Gateway (Public Switched Telephone Network) oder einem Session Initiation Protocol (SIP)-Trunk. In einigen Bereitstellungen werden auch die Medien selbst zwischen diesen Punkten übersetzt.
  
Auf der Seite von Skype for Business Server lauscht der Vermittlungsserver einer einzelnen TLS (Mutual TLS)-Transportadresse. Auf der Gatewayseite lauscht der Vermittlungsserver allen zugeordneten Abhörports, die Trunks zugeordnet sind. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.
  
Wenn Sie auch über eine öffentliche Nebenstellenanlage in Ihrer Umgebung verfügen, verarbeitet Vermittlungsserver Anrufe zwischen Enterprise-VoIP und der Nebenstellenanlage. Wenn ihre Nebenstellenanlage eine IP-PBX-Anlage ist, können Sie eine direkte SIP-Verbindung zwischen der Nebenstellenanlage und dem Vermittlungsserver erstellen. Wenn ihre Nebenstellenanlage eine Time Division Multiplex (TDM)-Nebenstellenanlage ist, müssen Sie auch ein PSTN-Gateway zwischen dem Vermittlungsserver und der Nebenstellenanlage bereitstellen.
  
Der Vermittlungsserver ist standardmäßig mit dem Front-End-Server kollidiert. Der Vermittlungsserver kann auch in einem eigenständigen Pool bereitgestellt werden.
  
## <a name="what-mediation-server-does"></a>Was der Vermittlungsserver macht

Die Hauptfunktionen des Vermittlungsservers sind:
  
- Verschlüsseln und Entschlüsseln von SRTP auf der Skype for Business Server-Seite. 
    
- Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über mutual TLS.
    
- Übersetzen von Mediendatenströmen zwischen Skype for Business Server und dem Gateway-Peer des Vermittlungsservers.
    
- Verbinden von Clients außerhalb des Netzwerks mit internen ICE-Komponenten, die die Medienquerung von NAT und Firewalls ermöglichen.
    
- Fungiert als Vermittler für Anrufflüsse, die von einem Gateway nicht unterstützt werden, z. B. Anrufe von Remotemitarbeitern Enterprise-VoIP clien.t
    
- In Bereitstellungen, die SIP-Trunking umfassen, arbeiten Sie mit dem SIP-Trunking-Dienstanbieter zusammen, um pstN-Unterstützung zu bieten, wodurch kein PSTN-Gateway mehr benötigt wird.
    
Die folgende Abbildung zeigt die Signal- und Medienprotokolle, die vom Vermittlungsserver bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP werden.
  
**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Diagramm "Vermittlungsserverprotokolle"](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Wenn Sie TCP oder RTP/RTCP (anstelle von SRTP oder SRTCP) im Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungsserver verwenden, wird empfohlen, Maßnahmen zu ergreifen, um die Sicherheit und den Datenschutz des Netzwerks sicherzustellen. 
  
## <a name="mn-trunk"></a>M:N-Trunk

Skype for Business Server unterstützt Flexibilität bei der Definition eines Trunks für Anrufroutingzwecke. Ein Trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver und der Nummer des Abhörports, mit einem Gateway und einer Nummer des Abhörports. Dies impliziert mehrere Dinge: Ein Vermittlungsserver kann mehrere Trunks zum gleichen Gateway haben. Ein Vermittlungsserver kann mehrere Trunks zu unterschiedlichen Gateways haben. Umgekehrt kann ein Gateway mehrere Trunks zu unterschiedlichen Vermittlungsservern haben.
  
Sie müssen weiterhin einen Stammstammstamm erstellen, wenn Sie ihrer Skype for Business-Topologie mithilfe des Topologie-Generators ein Gateway hinzufügen. Die Anzahl der Gateways, die von einem bestimmten Vermittlungsserver verarbeitet werden können, hängt von der Verarbeitungskapazität des Servers zu Spitzenzeiten ab. Wenn Sie einen Vermittlungsserver auf Hardware bereitstellen, der die Mindesthardwareanforderungen für Skype for Business Server erfüllt, wie unter Serveranforderungen für [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)beschrieben, kann ein eigenständiger Vermittlungsserver ungefähr 1000 Anrufe verarbeiten. Der Vermittlungsserver führt Transcoding durch, führt aber trotzdem Anrufe für mehrere Gateways weiter, auch wenn die Gateways keine Medienumgehung unterstützen.
  
Beim Definieren einer Anrufroute geben Sie die trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator zum Zuordnen von Trunks zu Vermittlungsservern. Das Routing bestimmt also, welcher Trunk für einen Anruf verwendet werden soll, und anschließend wird dem diesem Trunk zugeordneten Vermittlungsserver die Signalisierung für diesen Anruf gesendet.
  
Der Vermittlungsserver kann als Pool bereitgestellt werden. Dieser Pool kann mit einem Front-End-Pool oder als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungsserver mit einem Front-End-Pool zusammengeknallt ist, kann die Poolgröße mindestens 12 (der Grenzwert für die Größe des Registrierungspools) sein. Insgesamt erhöhen diese Funktionen die Zuverlässigkeit und Die Flexibilität der Bereitstellung für Vermittlungsserver, erfordern jedoch ähnliche Funktionen wie folgt:
  
- **PSTN-Gateway.** Ein qualifiziertes Skype for Business Server-Gateway muss den DNS-Lastenausgleich implementieren, wodurch ein qualifiziertes PstN-Gateway (Public Switched Telephone Network) als Lastenausgleich für einen Pool von Vermittlungsservern fungieren kann und dadurch anrufe über den Pool verteilt werden können.
    
- **Session Border Controller.** Bei einem SIP-Trunk ist die Peerentität ein Session Border Controller (SBC) bei einem Internettelefoniedienstanbieter. In richtung vom Vermittlungsserverpool zum SBC kann der SBC Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In richtung vom SBC zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Eine Methode, um dies zu erreichen, ist der DNS-Lastenausgleich, sofern vom Dienstanbieter und SBC unterstützt. Eine Alternative ist, dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool zu geben, und der Dienstanbieter bietet diese in ihrem SBC als separaten SIP-Trunk für jeden Vermittlungsserver an. Anschließend wird der Lastenausgleich für eigene Server vom Dienstanbieter ausgeführt. Möglicherweise unterstützen nicht alle Dienstanbieter oder SBCs diese Funktionen. Darüber hinaus kann der Dienstanbieter zusätzliche Gebühren für diese Funktion berechnen. In der Regel fallen für jeden SIP-Trunk an den SBC monatliche Gebühren an.
    
- **IP-PBX.** In Der Richtung vom Vermittlungsserverpool zum IP-PBX-SIP-Abschluss kann die IP-PBX Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung von der IP-PBX zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Da die IP-PBXs den DNS-Lastenausgleich nicht unterstützen, wird empfohlen, einzelne direkte SIP-Verbindungen von der IP-PBX zu jedem Vermittlungsserver im Pool zu definieren. Die IP-PBX übernimmt dann einen eigenen Lastenausgleich, indem der Datenverkehr über die Trunkgruppe verteilt wird. Es wird davon ausgegangen, dass die Trunkgruppe über einen konsistenten Satz von Routingregeln an der IP-PBX verfügt. Ob eine bestimmte IP-PBX dieses Trunkgruppenkonzept unterstützt und wie es sich mit der eigenen Redundanz- und Clusterarchitektur der IP-PBX überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungsservercluster ordnungsgemäß mit einer IP-PBX interagieren kann.
    
Ein Vermittlungsserverpool muss über eine einheitliche Ansicht des Peergateways verfügen, mit dem er interagiert. Dies bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher auf dieselbe Definition des Peergateways zugreifen und für ausgehende Anrufe mit ihm interagieren. Daher gibt es keine Möglichkeit, den Pool so zu segmentieren, dass einige Vermittlungsserver nur mit bestimmten Gateway-Peers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies wäre beispielsweise der Fall, wenn die zugeordneten Funktionen in PSTN-Gateways, SIP-Trunks oder IP-PBXs für die Interaktion mit einem Pool wie weiter oben in diesem Thema beschrieben nicht vorhanden sind.
  
Ein bestimmtes PSTN-Gateway, ein IP-PBX- oder sip-Trunk-Peer kann an mehrere Vermittlungsserver oder Trunks umstellen. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die Medienumgehung verwenden. Wenn eine große Anzahl von Anrufen die Medienumgehung verwendet, kann ein Vermittlungsserver im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung der Signalschicht erforderlich ist. 
  
## <a name="call-admission-control-and-mediation-server"></a>Anrufsteuerung und Vermittlungsserver

Anrufsteuerung (Call Admission Control, Anrufsteuerung) verwaltet die Einrichtung von Echtzeitsitzungen basierend auf der verfügbaren Bandbreite, um eine schlechte Qualität der Benutzererfahrung (Quality of Experience, QoE) für Benutzer in überlasteten Netzwerken zu verhindern. Um dies zu unterstützen, ist der Vermittlungsserver für die Bandbreitenverwaltung für seine beiden Interaktionen auf der Skype for Business Server-Seite und auf der Gatewayseite verantwortlich. Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung. Die Gateway-Peers (PSTN-Gateway, IP-PBX, SBC), mit denen der Vermittlungsserver auf Gatewayseite interagiert, unterstützen die Anrufsteuerung von Skype for Business Server nicht. Daher muss der Vermittlungsserver Bandbreiteninteraktionen im Auftrag seines Gateway-Peers verarbeiten. Wann immer möglich, reserviert der Vermittlungsserver die Bandbreite im Voraus. Ist dies nicht möglich (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert. Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.
  
Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung verwendet wird, wird für den Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden. Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, der den Vermittlungsserver umfasst, kann für diesen Anruf keine Medienumgehung verwendet werden.
  
Weitere Informationen zur Medienumgehung oder Anrufsteuerung finden Sie unter [Plan for media bypass in Skype for Business](media-bypass.md) oder Plan for call admission control in Skype for Business [Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver

Der Vermittlungsserver verfügt über erweiterte Funktionen, sodass er ordnungsgemäß mit erweiterten 9-1-1(E9-1-1)-Dienstanbietern interagieren kann. Auf dem Vermittlungsserver ist keine spezielle Konfiguration erforderlich. Die für die E9-1-1-Interaktion erforderlichen SIP-Erweiterungen sind standardmäßig im SIP-Protokoll des Vermittlungsservers für die Interaktionen mit einem Gateway peer (PSTN-Gateway, IP-PBX oder SBC eines Internettelefoniedienstanbieters, einschließlich E9-1-1-Dienstanbietern) enthalten.
  
Ob ein SIP-Trunk zu einem E9-1-1-Dienstanbieter in einem vorhandenen Vermittlungsserverpool terminiert werden kann oder eigenständige Vermittlungsserver erfordert, hängt davon ab, ob der E9-1-1-SBC mit einem Vermittlungsserverpool interagieren kann. Weitere Informationen finden Sie unter [M:N trunk in Skype for Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Medienumgehung und Vermittlungsserver

Die Medienumgehung ist eine Skype for Business Server-Funktion, mit der ein Administrator das Anrufrouting so konfigurieren kann, dass es direkt zwischen dem Benutzerendpunkt und dem PstN-Gateway (Public Switched Telephone Network) fließt, ohne den Vermittlungsserver zu durchlaufen. Die Medienumgehung verbessert die Anrufqualität, indem wartezeiten, unnötige Übersetzungen, die Möglichkeit von Paketverlusten und die Anzahl potenzieller Fehlerpunkte reduziert werden. Wenn ein Remotestandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, reduziert die Medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Remotestandort direkt an das lokale Gateway fließen können, ohne zuerst über die WAN-Verbindung zu einem Vermittlungsserver am zentralen Standort und zurück fließen zu müssen. Diese Reduzierung der Medienverarbeitung ergänzt auch die Fähigkeit des Vermittlungsservers, mehrere Gateways zu steuern.
  
Die Medienumgehung und die Anrufsteuerung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.
  
## <a name="topologies-for-mediation-server"></a>Topologien für Vermittlungsserver

Der Skype for Business Server, Vermittlungsserver, ist standardmäßig mit dem Standard Edition-Server, einem Front-End-Pool oder der Survivable Branch Appliance zusammenarbeitet. Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.
  
Wenn die Leistung ein Problem ist, ist es möglicherweise vorzuziehen, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool zu bereitstellen. Es wird auf jeden Fall ein eigenständiger Pool empfohlen, wenn Sie SIP-Trunking bereitstellen. 
  
Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger fea-mediation-pool erforderlich. Dies liegt daran, dass qualifizierte Gateways den DNS-Lastenausgleich zu einem Pool von Vermittlungsservern verwenden können und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen können.
  
Es wird außerdem empfohlen, den Vermittlungsserver in einem Front-End-Pool zu verbinden, wenn Sie IP-PBXs bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internettelefonieserveranbieters herstellen, solange eine der folgenden Bedingungen erfüllt ist:
  
- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.
    
- Die IP-PBX unterstützt keine Medienumgehung, aber der Front-End-Pool, der den Vermittlungsserver hosten soll, kann die Sprachtranscodierung für Anrufe verarbeiten, für die keine Medienumgehung gilt.
    
Sie können das Microsoft Lync Server 2013- Planungstool verwenden, um zu bewerten, ob der Front-End-Pool, in dem Sie den Vermittlungsserver verbinden möchten, die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
Die folgende Abbildung zeigt eine einfache Topologie, die aus zwei Standorten besteht, die über eine WAN-Verbindung verbunden sind. Der Vermittlungsserver ist in einem Front-End-Pool an Standort 1 zusammengeknallt. Die Vermittlungsserver an Standort 1 steuert sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2. In dieser Topologie ist die Medienumgehung global für die Verwendung von Standort- und Regioneninformationen aktiviert, und die Trunks für jedes PSTN-Gateway (GW1 und GW2) haben die Umgehung aktiviert.
  
**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![Voicetopologie mit Vermittlungsserver-WAN-Gateway](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Die nächste Abbildung zeigt eine einfache Topologie, in der vermittlungsserver im Front-End-Pool an Standort 1 verbunden ist und über eine direkte SIP-Verbindung mit der IP-PBX an Standort 1 verfügt. In dieser Abbildung steuert der Vermittlungsserver auch ein PSTN-Gateway an Standort 2. Angenommen, Skype for Business-Benutzer sind an den Standorten 1 und 2 vorhanden. Angenommen, die IP-PBX verfügt über einen zugeordneten Medienprozessor, der von allen Medien, die von Skype for Business-Endpunkten stammen, durchlaufen werden muss, bevor sie an medienendpunkte gesendet wird, die von der IP-PBX gesteuert werden. In dieser Topologie ist die Medienumgehung global für die Verwendung von Standort- und Regioneninformationen aktiviert, und die Trunks für die Nebenstellenanlage und das PSTN-Gateway haben die Medienumgehung aktiviert.
  
**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![VoiceTopology Mediation Server WAN PBX](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der der Vermittlungsserver mit dem SBC eines Internettelefoniedienstanbieters verbunden ist. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planungsentscheidungen für Vermittlungsserver

In diesem Thema werden Planungsentscheidungen beschrieben, die Sie für Ihre Vermittlungsserverbereitstellung treffen müssen.
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Kollokierter oder eigenständiger Vermittlungsserver?

Der Vermittlungsserver ist standardmäßig mit anderen Servern auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten verbunden. Die Anzahl der Telefonanrufe (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl der im Pool benötigten Computer hängt von den folgenden Bedingungen ab:
  
- Die Anzahl der Gateway peers, die der Vermittlungsserverpool steuert
    
- Die Zeiträume mit hohem Datenverkehr über diese Gateways
    
- Der Prozentsatz der Anrufe, deren Medien den Vermittlungsserver umgehen
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die nicht für die Medienumgehung konfiguriert sind, sowie die Verarbeitung, die erforderlich ist, um Signalinteraktionen für die Anzahl der Anrufe während der Arbeitsstunden zu verarbeiten, die unterstützt werden müssen. Wenn nicht genügend CPU verfügbar ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. und PSTN-Gateways, IP-PBXs und SBCs müssen in Teilmengen aufgeteilt werden, die von den zugeordneten Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-PBXs oder Session Border Controller (SBCs) bereitgestellt haben, die nicht die richtigen Funktionen für die Interaktion mit einem Pool von Vermittlungsservern unterstützen, einschließlich der folgenden, müssen sie einem eigenständigen Pool zugeordnet werden, der aus einem einzelnen Vermittlungsserver besteht:
  
- Durchführen des Lastenausgleichs des Domänennamenssystems (Domain Name System, DNS) über Vermittlungsserver in einem Pool (oder anderweitige einheitliches Routen des Datenverkehrs an alle Vermittlungsserver in einem Pool)
    
- Akzeptieren von Datenverkehr von jedem Vermittlungsserver in einem Pool
    
Sie können das Microsoft Lync Server 2013- Planungstool verwenden, um zu bewerten, ob das Verbinden des Vermittlungsservers mit Ihrem Front-End-Pool die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
### <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Bei Bereitstellung von SIP-Trunks müssen Sie jedoch einen Vermittlungsserver an dem Standort bereitstellen, der als Endpunkt für die einzelnen Trunks dient. Bei Einsatz eines Vermittlungsservers am zentralen Standort zum Weiterleiten von Anrufen für eine IP-Nebenstellenanlage oder ein PSTN-Gateway an einem Zweigstellenstandort ist keine Medienumgehung erforderlich. Wenn Sie jedoch die Medienumgehung aktivieren können, wird dadurch die Medienpfadlatenz reduziert und die Medienqualität verbessert, da der Medienpfad nicht mehr zum Folgen des Signalpfads erforderlich ist. Die Medienumgehung verringert auch die Verarbeitungslast für den Pool.
  
> [!NOTE]
> Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter [Unified Communications Open Interoperability Program - Lync Server aufgeführt sind.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 
  
Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Bei ausfallsicheren Zweigstellenstandorten wird davon ausgegangen, dass Anwesenheit und Konferenzen am Standort nicht ausfallsicher sind.) Anleitungen zur Planung von Zweigstellenstandorten für Voice finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
  
Wenn die IP-PBX bei Interaktionen mit einer IP-PBX frühe Medieninteraktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, können die ersten Wörter der Begrüßung für eingehende Anrufe von der IP-PBX an Skype for Business-Endpunkte abgeschnitten werden. Dieses Problem kann schwerwiegender sein, wenn ein Vermittlungsserver an einem zentralen Standort Anrufe für eine IP-PBX weiterleite, an der die Route an einem Zweigstellenstandort endet, da mehr Zeit für die Signalisierung erforderlich ist. Wenn Sie dieses Verhalten erleben, ist die Bereitstellung eines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit, die Beschneidung der ersten Wörter zu reduzieren.
  
Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.
  
> [!NOTE]
> Um die Medienleistung des eigenständigen Vermittlungsservers zu verbessern, sollten Sie die empfangsseitige Skalierung (RSS) auf den Netzwerkadaptern auf diesen Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie [unter "Receive-Side Scaling Enhancements in Windows Server"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)). Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Netzwerkadapterdokumentation. 
