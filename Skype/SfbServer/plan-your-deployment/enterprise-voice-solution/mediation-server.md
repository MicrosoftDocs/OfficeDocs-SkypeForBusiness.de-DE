---
title: Vermittlungsserverkomponente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Erfahren Sie mehr über Vermittlungsserver in Skype for Business Server, einschließlich der unterstützten Topologien und der Beziehungen zu M:N-Trunks, Medienumgehung und Anrufsteuerung.
ms.openlocfilehash: 10d35081e1b6af1d7ee634fa3507a9c6d46f3954
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861172"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Vermittlungsserverkomponente in Skype for Business Server
 
Erfahren Sie mehr über Vermittlungsserver in Skype for Business Server, einschließlich der unterstützten Topologien und der Beziehungen zu M:N-Trunks, Medienumgehung und Anrufsteuerung.
  
Um Enterprise-VoIP bereitzustellen, müssen Sie einen oder mehrere Vermittlungsserver bereitstellen. 
  
Der Vermittlungsserver übersetzt die Signalisierung zwischen Ihrer internen Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem SIP-Trunk (Session Initiation Protocol). In einigen Bereitstellungen werden auch die Medien selbst zwischen diesen Punkten übersetzt.
  
Auf der Skype for Business Server Seite überwacht der Vermittlungsserver eine einzelne MTLS-Transportadresse (Mutual Mutual TLS). Auf der Gatewayseite überwacht der Vermittlungsserver alle zugehörigen Überwachungsports, die Trunks zugeordnet sind. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.
  
Wenn Sie auch über eine vorhandene Nebenstellenanlage (Public Branch Exchange) in Ihrer Umgebung verfügen, verarbeitet der Vermittlungsserver Anrufe zwischen Enterprise-VoIP Benutzern und der Nebenstellenanlage. Wenn Es sich bei Ihrer Nebenstellenanlage um eine IP-Nebenstellenanlage handelt, können Sie eine direkte SIP-Verbindung zwischen der Nebenstellenanlage und dem Vermittlungsserver herstellen. Wenn Ihre Nebenstellenanlage eine TDM-Nebenstellenanlage (Time Division Multiplex) ist, müssen Sie auch ein PSTN-Gateway zwischen dem Vermittlungsserver und der Nebenstellenanlage bereitstellen.
  
Der Vermittlungsserver ist standardmäßig mit dem Front-End-Server verbunden. Der Vermittlungsserver kann auch in einem eigenständigen Pool bereitgestellt werden.
  
## <a name="what-mediation-server-does"></a>Funktion des Vermittlungsservers

Die wichtigsten Funktionen des Vermittlungsservers sind:
  
- Verschlüsseln und Entschlüsseln von SRTP auf der Skype for Business Server Seite. 
    
- Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über gegenseitiges TLS.
    
- Übersetzen von Mediendatenströmen zwischen Skype for Business Server und dem Gatewaypeer des Vermittlungsservers.
    
- Verbinden von Clients außerhalb des Netzwerks mit internen ICE-Komponenten, die die Mediendurchquerung von NAT und Firewalls ermöglichen.
    
- Als Vermittler für Anrufflüsse fungieren, die von einem Gateway nicht unterstützt werden, z. B. Anrufe von Remotemitarbeitern an einer Enterprise-VoIP clien.t
    
- Bei Bereitstellungen, die SIP-Trunking enthalten, arbeiten Sie mit dem SIP-Trunkingdienstanbieter zusammen, um PSTN-Unterstützung bereitzustellen, wodurch kein PSTN-Gateway erforderlich ist.
    
Die folgende Abbildung zeigt die Signal- und Medienprotokolle, die vom Vermittlungsserver bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP-Infrastruktur verwendet werden.
  
**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Diagramm "Vermittlungsserverprotokolle".](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Wenn Sie TCP oder RTP/RTCP (anstelle von SRTP oder SRTCP) im Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungsserver verwenden, empfehlen wir, Maßnahmen zu ergreifen, um die Sicherheit und den Datenschutz des Netzwerks zu gewährleisten. 
  
## <a name="mn-trunk"></a>M:N-Trunk

Skype for Business Server unterstützt flexibilität bei der Definition eines Trunks für Anrufweiterleitungszwecke. Ein Trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver und einer Überwachungsportnummer mit einem Gateway und einer Überwachungsportnummer. Dies impliziert mehrere Dinge: Ein Vermittlungsserver kann mehrere Trunks zum gleichen Gateway haben; Ein Vermittlungsserver kann mehrere Trunks zu unterschiedlichen Gateways haben. Umgekehrt kann ein Gateway mehrere Trunks zu verschiedenen Vermittlungsservern haben.
  
Sie müssen weiterhin einen Stammtrunk erstellen, wenn Sie ihrer Skype for Business Topologie mithilfe des Topologie-Generators ein Gateway hinzufügen. Die Anzahl der Gateways, die ein bestimmter Vermittlungsserver verarbeiten kann, hängt von der Verarbeitungskapazität des Servers während der Spitzenzeiten ab. Wenn Sie einen Vermittlungsserver auf Hardware bereitstellen, die die Mindesthardwareanforderungen für Skype for Business Server erfüllt, wie in den [Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)beschrieben, kann ein eigenständiger Vermittlungsserver ca. 1000 Anrufe verarbeiten. Der Vermittlungsserver führt die Transcodierung durch, leitet jedoch weiterhin Anrufe für mehrere Gateways weiter, auch wenn die Gateways keine Medienumgehung unterstützen.
  
Beim Definieren einer Anrufroute geben Sie die trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator, um Trunks Vermittlungsservern zuzuordnen. Das Routing bestimmt also, welcher Trunk für einen Anruf verwendet werden soll, und anschließend wird dem diesem Trunk zugeordneten Vermittlungsserver die Signalisierung für diesen Anruf gesendet.
  
Der Vermittlungsserver kann als Pool bereitgestellt werden. Dieser Pool kann mit einem Front-End-Pool verbunden oder als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungsserver mit einem Front-End-Pool verbunden ist, kann die Poolgröße maximal 12 (der Grenzwert der Poolgröße der Registrierungsstelle) sein. Zusammengenommen erhöhen diese Funktionen die Zuverlässigkeit und Bereitstellungsflexibilität für Vermittlungsserver, erfordern jedoch ähnliche Funktionen in den folgenden Bereichen:
  
- **PSTN-Gateway.** Ein Skype for Business Server qualifizierte Gateway muss einen DNS-Lastenausgleich implementieren, der es einem qualifizierten PSTN-Gateway (Public Switched Telephone Network) ermöglicht, als Lastenausgleich für einen Pool von Vermittlungsservern zu fungieren und dadurch Anrufe über den Pool zu verteilen.
    
- **Session Border Controller.** Bei einem SIP-Trunk ist die Peerentität ein Session Border Controller (SBC) bei einem Anbieter von Internettelefoniediensten. In richtung vom Vermittlungsserverpool zum SBC kann der SBC Verbindungen von jedem Vermittlungsserver im Pool empfangen. In der Richtung vom SBC zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Eine Methode, dies zu erreichen, ist der DNS-Lastenausgleich, sofern dies vom Dienstanbieter und SBC unterstützt wird. Eine Alternative besteht darin, dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool zu geben, und der Dienstanbieter stellt diese auf dem SBC als separaten SIP-Trunk für jeden Vermittlungsserver bereit. Der Dienstanbieter übernimmt dann den Lastenausgleich für seine eigenen Server. Nicht alle Dienstanbieter oder SBCs unterstützen diese Funktionen möglicherweise. Darüber hinaus kann der Dienstanbieter für diese Funktion zusätzliche Gebühren berechnen. In der Regel wird für jeden SIP-Trunk zum SBC eine monatliche Gebühr berechnet.
    
- **IP-Nebenstellenanlage.** In Richtung vom Vermittlungsserverpool zum IP-PBX-SIP-Ende kann die IP-Nebenstellenanlage Verbindungen von jedem Vermittlungsserver im Pool empfangen. In richtung von der IP-Nebenstellenanlage an den Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Da die meisten IP-PBXs den DNS-Lastenausgleich nicht unterstützen, empfehlen wir, dass einzelne direkte SIP-Verbindungen von der IP-Nebenstellenanlage zu jedem Vermittlungsserver im Pool definiert werden. Die IP-Nebenstellenanlage übernimmt dann ihren eigenen Lastenausgleich, indem der Datenverkehr über die Trunkgruppe verteilt wird. Es wird davon ausgegangen, dass die Trunkgruppe über einen konsistenten Satz von Routingregeln an der IP-Nebenstellenanlage verfügt. Ob eine bestimmte IP-Nebenstellenanlage dieses Trunkgruppenkonzept unterstützt und wie es sich mit der Redundanz- und Clusterarchitektur der IP-Nebenstellenanlage überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungsservercluster ordnungsgemäß mit einer IP-Nebenstellenanlage interagieren kann.
    
Ein Vermittlungsserverpool muss über eine einheitliche Ansicht des Peergateways verfügen, mit dem er interagiert. Dies bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher auf die gleiche Definition des Peergateways zugreifen und wahrscheinlich auch für ausgehende Anrufe damit interagieren. Daher gibt es keine Möglichkeit, den Pool so zu segmentieren, dass einige Vermittlungsserver nur mit bestimmten Gatewaypeers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies wäre beispielsweise der Fall, wenn die zugeordneten Funktionen in PSTN-Gateways, SIP-Trunks oder IP-PBXs für die Interaktion mit einem Pool nicht vorhanden sind, wie weiter oben in diesem Thema beschrieben.
  
Ein bestimmtes PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SIP-Trunkpeer kann an mehrere Vermittlungsserver oder Trunks weitergeleitet werden. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die Medienumgehung verwenden. Wenn eine große Anzahl von Anrufen die Medienumgehung verwendet, kann ein Vermittlungsserver im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung der Signalschicht erforderlich ist. 
  
## <a name="call-admission-control-and-mediation-server"></a>Anrufsteuerung und Vermittlungsserver

Die Anrufsteuerung (Call Admission Control, CAC) verwaltet die Einrichtung von Echtzeitsitzungen basierend auf der verfügbaren Bandbreite, um eine schlechte QoE (Quality of Experience) für Benutzer in überlasteten Netzwerken zu verhindern. Um dies zu unterstützen, ist der Vermittlungsserver für die Bandbreitenverwaltung für seine beiden Interaktionen auf der Skype for Business Server- und der Gatewayseite verantwortlich. Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung. Die Gatewaypeers (PSTN-Gateway, IP-Nebenstellenanlage, SBC), mit denen der Vermittlungsserver auf der Gatewayseite interagiert, unterstützen Skype for Business Server Anrufsteuerung nicht. Daher muss der Vermittlungsserver Bandbreiteninteraktionen im Namen seines Gatewaypeers verarbeiten. Nach Möglichkeit reserviert der Vermittlungsserver die Bandbreite im Voraus. Ist dies nicht möglich (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert. Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.
  
Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung verwendet wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden. Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, der den Vermittlungsserver umfasst, kann für diesen Anruf keine Medienumgehung verwendet werden.
  
Ausführliche Informationen zur Medienumgehung oder Anrufsteuerung finden Sie unter [Plan for media bypass in Skype for Business](media-bypass.md) or Plan for call admission control in [Skype for Business Server.](call-admission-control.md)
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver

Der Vermittlungsserver verfügt über erweiterte Funktionen, sodass er ordnungsgemäß mit E9-1-1-Dienstanbietern (Enhanced 9-1-1) interagieren kann. Auf dem Vermittlungsserver ist keine spezielle Konfiguration erforderlich. Die für die E9-1-1-Interaktion erforderlichen SIP-Erweiterungen sind standardmäßig im SIP-Protokoll des Vermittlungsservers für die Interaktionen mit einem Gatewaypeer (PSTN-Gateway, IP-Nebenstellenanlage oder dem SBC eines Internettelefoniedienstanbieters, einschließlich E9-1-1-Dienstanbietern) enthalten.
  
Ob ein SIP-Trunk zu einem E9-1-1-Dienstanbieter in einem vorhandenen Vermittlungsserverpool terminiert werden kann oder eigenständige Vermittlungsserver erfordert, hängt davon ab, ob der E9-1-1-SBC mit einem Vermittlungsserverpool interagieren kann. Ausführliche Informationen finden Sie unter [M:N-Trunk in Skype for Business Server.](m-n-trunk.md)
  
## <a name="media-bypass-and-mediation-server"></a>Medienumgehung und Vermittlungsserver

Bei der Medienumgehung handelt es sich um eine Skype for Business Server Funktion, mit der ein Administrator das Anrufrouting so konfigurieren kann, dass es direkt zwischen dem Benutzerendpunkt und dem PSTN-Gateway (Public Switched Telephone Network) erfolgt, ohne den Vermittlungsserver zu durchlaufen. Die Medienumgehung verbessert die Anrufqualität, indem Latenz, unnötige Übersetzung, Paketverluste und die Anzahl potenzieller Fehlerquellen reduziert werden. Wenn ein Remotestandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit beschränkter Bandbreite mit einem zentralen Standort verbunden ist, verringert die Medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Remotestandort direkt zu seinem lokalen Gateway fließen können, ohne zuerst über die WAN-Verbindung zu einem Vermittlungsserver am zentralen Standort und zurück fließen zu müssen. Diese Reduzierung der Medienverarbeitung ergänzt auch die Fähigkeit des Vermittlungsservers, mehrere Gateways zu steuern.
  
Die Medienumgehung und die Anrufsteuerung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.
  
## <a name="topologies-for-mediation-server"></a>Topologien für Vermittlungsserver

Der Skype for Business Server Vermittlungsserver ist standardmäßig mit Standard Edition Server, einem Front-End-Pool oder einer Survivable Branch Appliance verbunden. Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.
  
Wenn die Leistung ein Problem darstellt, kann es vorzuziehen sein, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitzustellen. Wir empfehlen auf jeden Fall einen eigenständigen Pool, wenn Sie SIP-Trunking bereitstellen. 
  
Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger fea-mediation-pool erforderlich. Dies liegt daran, dass qualifizierte Gateways einen DNS-Lastenausgleich zu einem Pool von Vermittlungsservern durchführen können und Datenverkehr von jedem Vermittlungsserver in einem Pool empfangen können.
  
Außerdem wird empfohlen, dass Sie den Vermittlungsserver in einem Front-End-Pool verbinden, wenn Sie IP-PBXs bereitgestellt oder eine Verbindung mit dem Session Border Controller (SBC) eines Internettelefonieserveranbieters hergestellt haben, solange eine der folgenden Bedingungen erfüllt ist:
  
- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.
    
- Die IP-Nebenstellenanlage unterstützt keine Medienumgehung, aber der Front-End-Pool, der den Vermittlungsserver hostet, kann die Sprachtranscodierung für Anrufe verarbeiten, für die die Medienumgehung nicht gilt.
    
Sie können das Microsoft Lync Server 2013-Planungstool verwenden, um zu bewerten, ob der Front-End-Pool, in dem Sie den Vermittlungsserver verbinden möchten, die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
Die folgende Abbildung zeigt eine einfache Topologie, die aus zwei Standorten besteht, die über eine WAN-Verbindung verbunden sind. Der Vermittlungsserver ist in einem Front-End-Pool am Standort 1 verbunden. Die Vermittlungsserver am Standort 1 steuern sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2. In dieser Topologie ist die Medienumgehung global für die Verwendung von Standort- und Regionsinformationen aktiviert, und für die Trunks zu jedem PSTN-Gateway (GW1 und GW2) ist die Umgehung aktiviert.
  
**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![VoIP-Topologie mit VERMITTLUNGsserver-WAN-Gateway.](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Die nächste Abbildung zeigt eine einfache Topologie, in der der Vermittlungsserver im Front-End-Pool am Standort 1 verbunden ist und über eine direkte SIP-Verbindung mit der IP-Nebenstellenanlage am Standort 1 verfügt. In dieser Abbildung steuert der Vermittlungsserver auch ein PSTN-Gateway am Standort 2. Gehen Sie davon aus, dass Skype for Business Benutzer sowohl auf Websites 1 als auch auf 2 vorhanden sind. Gehen Sie außerdem davon aus, dass die IP-Nebenstellenanlage über einen zugeordneten Medienprozessor verfügt, der von allen Medien durchlaufen werden muss, die von Skype for Business Endpunkten stammen, bevor sie an Medienendpunkte gesendet werden, die von der IP-Nebenstellenanlage gesteuert werden. In dieser Topologie ist die Medienumgehung global für die Verwendung von Standort- und Regionsinformationen aktiviert, und für die Trunks zur Nebenstellenanlage und dem PSTN-Gateway ist die Medienumgehung aktiviert.
  
**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![Voice Topology Mediation Server WAN PBX.](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der der Vermittlungsserver mit dem SBC eines Internettelefoniedienstanbieters verbunden ist. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planungsentscheidungen für Vermittlungsserver

In diesem Thema werden Planungsentscheidungen beschrieben, die Sie für Ihre Vermittlungsserverbereitstellung treffen müssen.
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Verbundener oder eigenständiger Vermittlungsserver?

Der Vermittlungsserver ist standardmäßig mit anderen Servern auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten verbunden. Die Anzahl der PsTN-Anrufe (Public Switched Telephone Network), die verarbeitet werden können, und die Anzahl der im Pool erforderlichen Computer hängt von Folgenden ab:
  
- Die Anzahl der Gatewaypeers, die der Vermittlungsserverpool steuert
    
- Die Datenverkehrszeiträume mit hohem Datenverkehr über diese Gateways
    
- Der Prozentsatz der Anrufe, bei denen es sich um Anrufe handelt, deren Medien den Vermittlungsserver umgehen
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die nicht für die Medienumgehung konfiguriert sind, sowie die Verarbeitung, die erforderlich ist, um Signalinteraktionen für die Anzahl der Anrufe zu Spitzenzeiten zu verarbeiten, die unterstützt werden müssen. Wenn nicht genügend CPU vorhanden ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. und PSTN-Gateways, IP-Nebenstellenanlagen und SBCs müssen in Teilmengen aufgeteilt werden, die von den verbundenen Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs (Session Border Controller) bereitgestellt haben, die nicht die richtigen Funktionen für die Interaktion mit einem Pool von Vermittlungsservern unterstützen, einschließlich der folgenden, müssen sie einem eigenständigen Pool zugeordnet werden, der aus einem einzelnen Vermittlungsserver besteht:
  
- Durchführen eines DNS-Lastenausgleichs (Domain Name System) auf Netzwerkebene über Vermittlungsserver in einem Pool (oder anderweitiges einheitliches Weiterleiten des Datenverkehrs an alle Vermittlungsserver in einem Pool)
    
- Akzeptieren von Datenverkehr von jedem Vermittlungsserver in einem Pool
    
Sie können das Microsoft Lync Server 2013-Planungstool verwenden, um zu bewerten, ob das Verbinden des Vermittlungsservers mit Ihrem Front-End-Pool die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
### <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Bei Bereitstellung von SIP-Trunks müssen Sie jedoch einen Vermittlungsserver an dem Standort bereitstellen, der als Endpunkt für die einzelnen Trunks dient. Bei Einsatz eines Vermittlungsservers am zentralen Standort zum Weiterleiten von Anrufen für eine IP-Nebenstellenanlage oder ein PSTN-Gateway an einem Zweigstellenstandort ist keine Medienumgehung erforderlich. Wenn Sie jedoch die Medienumgehung aktivieren können, reduziert dies die Latenz des Medienpfads und verbessert die Medienqualität, da der Medienpfad nicht mehr dem Signalpfad folgen muss. Die Medienumgehung verringert auch die Verarbeitungslast für den Pool.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit jedem PSTN-Gateway, IP-PBX und SBC. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter [Unified Communications Open Interoperability Program – Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) aufgeführt sind. 
  
Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Bei der Ausfallsicherheit von Zweigstellenstandorten wird davon ausgegangen, dass Anwesenheits- und Konferenzfunktionen am Standort nicht ausfallsicher sind.) Anleitungen zur Planung von Zweigstellen für VoIP finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
  
Wenn die IP-Nebenstellenanlage bei Interaktionen mit einer IP-Nebenstellenanlage frühe Medieninteraktionen mit mehreren frühen Dialogfeldern und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, können die ersten Wörter der Begrüßung für eingehende Anrufe von der IP-Nebenstellenanlage an Skype for Business Endpunkte beschnitten werden. Dieses Problem kann schwerwiegender sein, wenn ein Vermittlungsserver an einem zentralen Standort Anrufe für eine IP-Nebenstellenanlage weiterleitet, bei der die Route an einem Zweigstellenstandort beendet wird, da mehr Zeit erforderlich ist, um die Signalisierung abzuschließen. Wenn dieses Verhalten vorliegt, ist die Bereitstellung eines Vermittlungsservers an der Zweigstelle die einzige Möglichkeit, die Beschneidung der ersten Wörter zu reduzieren.
  
Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.
  
> [!NOTE]
> Um die Medienleistung des eigenständigen Vermittlungsservers zu verbessern, sollten Sie RSS (Receive-Side Scaling) auf den Netzwerkadaptern auf diesen Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter ["Receive-Side Scaling Enhancements in Windows Server".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zum Netzwerkadapter. 
