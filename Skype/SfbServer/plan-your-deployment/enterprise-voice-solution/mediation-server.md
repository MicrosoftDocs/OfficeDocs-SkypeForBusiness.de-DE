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
description: Erfahren Sie mehr über Vermittlungsserver in Skype for Business Server, einschließlich der unterstützten Topologien und der Beziehungen zu M:N-Trunks, Medienumgehung und Anrufsteuerung.
ms.openlocfilehash: 14cf5fff38146622467698ffa58ccb244fac8fad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813675"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Vermittlungsserverkomponente in Skype for Business Server
 
Erfahren Sie mehr über Vermittlungsserver in Skype for Business Server, einschließlich der unterstützten Topologien und der Beziehungen zu M:N-Trunks, Medienumgehung und Anrufsteuerung.
  
Zum Bereitstellen Enterprise-VoIP Vermittlungsserver müssen Sie einen oder mehrere Vermittlungsserver bereitstellen. 
  
Der Vermittlungsserver übersetzt Signale zwischen Ihrer internen Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem Session Initiation Protocol (SIP)-Trunk. In einigen Bereitstellungen werden auch die Medien selbst zwischen diesen Punkten übersetzt.
  
Auf der Skype for Business Server-Seite lauscht der Vermittlungsserver an einer einzelnen MTLS (Mutual TLS)-Transportadresse. Auf der Gatewayseite lauscht der Vermittlungsserver an allen zugeordneten Listening Ports, die Trunks zugeordnet sind. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.
  
Wenn in Ihrer Umgebung auch eine Nebenstellenanlage (Public Branch Exchange, PBX) vorhanden ist, verarbeitet der Vermittlungsserver Anrufe zwischen Enterprise-VoIP und der Nebenstellenanlage. Wenn ihre Nebenstellenanlage eine IP-PBX-Anlage ist, können Sie eine direkte SIP-Verbindung zwischen der Nebenstellenanlage und dem Vermittlungsserver herstellen. Wenn es sich bei Ihrer Nebenstellenanlage um eine TDM-PBX -Anlage (Time Division Multiplex) handelt, müssen Sie auch ein PstN-Gateway zwischen dem Vermittlungsserver und der Nebenstellenanlage bereitstellen.
  
Der Vermittlungsserver ist standardmäßig mit dem Front-End-Server ausgeführt. Der Vermittlungsserver kann auch in einem eigenständigen Pool bereitgestellt werden.
  
## <a name="what-mediation-server-does"></a>Was der Vermittlungsserver macht

Die Wichtigsten Funktionen des Vermittlungsservers sind:
  
- Verschlüsseln und Entschlüsseln von SRTP auf der Skype for Business Server-Seite. 
    
- Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über MUTUAL TLS.
    
- Übersetzen von Mediendatenströmen zwischen Skype for Business Server und dem Gateway-Peer des Vermittlungsservers.
    
- Verbinden von Clients außerhalb des Netzwerks mit internen ICE-Komponenten, die das Durchlaufen von NAT und Firewalls durch Medien ermöglichen.
    
- Als Vermittler für Anrufflüsse zu agieren, die von einem Gateway nicht unterstützt werden, z. B. Anrufe von Remotemitarbeitern Enterprise-VoIP Clien.t
    
- In Bereitstellungen, die sip-Trunking umfassen, arbeiten Sie mit dem Sip-Trunking-Dienstanbieter zusammen, um PSTN-Unterstützung zu bieten, wodurch die Notwendigkeit eines PSTN-Gateways entfällt.
    
Die folgende Abbildung zeigt die Signal- und Medienprotokolle, die vom Vermittlungsserver bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP werden.
  
**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Diagramm mit Vermittlungsserverprotokollen](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Wenn Sie TCP oder RTP/RTCP (anstelle von SRTP oder SRTCP) im Netzwerk zwischen dem PstN-Gateway und dem Vermittlungsserver verwenden, sollten Sie Maßnahmen ergreifen, um die Sicherheit und den Datenschutz des Netzwerks sicherzustellen. 
  
## <a name="mn-trunk"></a>M:N-Trunk

Skype for Business Server unterstützt flexibilität bei der Definition eines Trunks für Anrufroutingzwecke. Ein Trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver und der Nummer des Abhörports mit einem Gateway und einer Nummer für den Abhörport. Dies impliziert mehrere Dinge: Ein Vermittlungsserver kann mehrere Trunks zum gleichen Gateway haben; Ein Vermittlungsserver kann mehrere Trunks zu unterschiedlichen Gateways haben; Umgekehrt kann ein Gateway mehrere Trunks zu unterschiedlichen Vermittlungsservern haben.
  
Sie müssen dennoch einen Stamm trunk erstellen, wenn Sie ihrer Skype for Business-Topologie mithilfe des Topologie-Generators ein Gateway hinzufügen. Die Anzahl der Gateways, die von einem bestimmten Vermittlungsserver verarbeitet werden können, hängt von der Verarbeitungskapazität des Servers zu Spitzenzeiten ab. Wenn Sie einen Vermittlungsserver auf Hardware bereitstellen, die die Mindesthardwareanforderungen für Skype for Business Server erfüllt, wie in den Serveranforderungen für [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)beschrieben, kann ein eigenständiger Vermittlungsserver ca. 1.000 Anrufe verarbeiten. Der Vermittlungsserver führt eine Transcodierung durch, führt aber dennoch Anrufe für mehrere Gateways weiter, auch wenn die Gateways keine Medienumgehung unterstützen.
  
Beim Definieren einer Anrufroute geben Sie die dieser Route zugeordneten Trunks an, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator, um Trunks Vermittlungsservern zuzuordnen. Das Routing bestimmt also, welcher Trunk für einen Anruf verwendet werden soll, und anschließend wird dem diesem Trunk zugeordneten Vermittlungsserver die Signalisierung für diesen Anruf gesendet.
  
Der Vermittlungsserver kann als Pool bereitgestellt werden. Dieser Pool kann mit einem Front-End-Pool oder als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungsserver mit einem Front-End-Pool ausgeführt wird, kann die Poolgröße bis zu 12 (die Beschränkung der Größe des Registrierungspools) sein. Zusammen erhöhen diese Funktionen die Zuverlässigkeit und Flexibilität bei der Bereitstellung von Vermittlungsservern, erfordern jedoch ähnliche Funktionen wie die folgenden:
  
- **PSTN-Gateway.** Ein qualifiziertes Skype for Business Server-Gateway muss einen DNS-Lastenausgleich implementieren, der es einem qualifizierten PSTN-Gateway (Public Switched Telephone Network) ermöglicht, als Lastenausgleich für einen Pool von Vermittlungsservern zu fungieren und dadurch einen Lastenausgleich für Anrufe im Pool zu ermöglichen.
    
- **Session Border Controller.** Bei einem SIP-Trunk ist die Peerentität ein Session Border Controller (SBC) bei einem Anbieter von Internettelefoniediensten. In Richtung des Vermittlungsserverpools zum SBC kann der SBC Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In Richtung des SBC zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Eine Möglichkeit, dies zu erreichen, ist der DNS-Lastenausgleich, sofern dies vom Dienstanbieter und SBC unterstützt wird. Alternativ können Sie dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool bereitstellen, und der Dienstanbieter wird diese in ihrem SBC als separater SIP-Trunk für jeden Vermittlungsserver bereitstellen. Der Dienstanbieter wird dann den Lastenausgleich für seine eigenen Server übernehmen. Nicht alle Dienstanbieter oder SBCs unterstützen diese Funktionen. Darüber hinaus kann der Dienstanbieter zusätzliche Gebühren für diese Funktion berechnen. In der Regel fallen für jeden SIP-Trunk zum SBC monatliche Gebühren an.
    
- **IP-PBX.** In richtung des Vermittlungsserverpools zur IP-PBX-SIP-Beendigung kann die IP-PBX-Anlage Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In Richtung der IP-PBX-Anlage zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Da die IP-PBXs keine Unterstützung für den DNS-Lastenausgleich bieten, empfiehlt es sich, einzelne direkte SIP-Verbindungen von der IP-PBX-Anlage zu jedem Vermittlungsserver im Pool zu definieren. Die IP-PBX-Anlage übernimmt dann einen eigenen Lastenausgleich, indem der Datenverkehr über die Trunkgruppe verteilt wird. Es wird davon ausgegangen, dass die Trunkgruppe über einen konsistenten Satz von Routingregeln an der IP-PBX-Anlage verfügt. Ob eine bestimmte IP-PBX-Anlage dieses Trunkgruppenkonzept unterstützt und wie es sich mit der eigenen Redundanz- und Clusterarchitektur der IP-PBX überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungsservercluster ordnungsgemäß mit einer IP-PBX-Anlage interagieren kann.
    
Ein Vermittlungsserverpool muss über eine einheitliche Ansicht des Peergateways verfügen, mit dem er interagiert. Dies bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher auf dieselbe Definition des Peergateways zugreifen und mit gleicher Wahrscheinlichkeit für ausgehende Anrufe damit interagieren. Daher gibt es keine Möglichkeit, den Pool so zu segmentieren, dass einige Vermittlungsserver nur mit bestimmten Gateway peers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies wäre beispielsweise der Fall, wenn die zugeordneten Funktionen in PSTN-Gateways, -SIP-Trunks oder IP-PBXs für die Interaktion mit einem Pool wie weiter oben in diesem Thema beschrieben nicht vorhanden sind.
  
Ein bestimmtes PSTN-Gateway, eine IP-PBX-Anlage oder ein SIP-Trunk-Peer kann an mehrere Vermittlungsserver oder Trunks geroutet werden. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die Medienumgehung verwenden. Wenn für eine große Anzahl von Anrufen die Medienumgehung verwendet wird, kann ein Vermittlungsserver im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung der Signalschicht erforderlich ist. 
  
## <a name="call-admission-control-and-mediation-server"></a>Anrufsteuerung und Vermittlungsserver

Die Anrufsteuerung verwaltet die Einrichtung von Echtzeitsitzungen basierend auf der verfügbaren Bandbreite, um eine schlechte QoE (Quality of Experience) für Benutzer in überlasteten Netzwerken zu verhindern. Um dies zu unterstützen, ist der Vermittlungsserver für die Bandbreitenverwaltung für seine beiden Interaktionen auf der Skype for Business Server-Seite und auf der Gatewayseite verantwortlich. Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung. Die Gateway-Peers (PSTN-Gateway, IP-PBX, SBC), mit denen der Vermittlungsserver auf Gatewayseite interagiert, unterstützen keine Skype for Business Server-Anrufsteuerung. Daher muss der Vermittlungsserver Bandbreiteninteraktionen im Namen seines Gateway-Peers verarbeiten. Nach Möglichkeit reserviert der Vermittlungsserver die Bandbreite im Voraus. Ist dies nicht möglich (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert. Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.
  
Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung verwendet wird, wird für den Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden. Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, der den Vermittlungsserver umfasst, kann für diesen Anruf keine Medienumgehung verwendet werden.
  
Weitere Informationen zur Medienumgehung oder Anrufsteuerung finden Sie unter ["Plan for media bypass in Skype for Business"](media-bypass.md) oder ["Plan for call admission control in Skype for Business Server".](call-admission-control.md)
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver

Der Vermittlungsserver verfügt über erweiterte Funktionen, sodass er ordnungsgemäß mit Dienstanbietern für erweiterte 9-1-1 -Dienste (E9-1-1) interagieren kann. Auf dem Vermittlungsserver ist keine spezielle Konfiguration erforderlich. Die für die E9-1-1-Interaktion erforderlichen SIP-Erweiterungen sind standardmäßig im Vermittlungsserver-SIP-Protokoll für die Interaktionen mit einem Gateway peer (PSTN-Gateway, IP-PBX oder SBC eines Anbieters für Internettelefoniedienste, einschließlich E9-1-1-Dienstanbietern) enthalten.
  
Ob ein SIP-Trunk zu einem E9-1-1-Dienstanbieter in einem vorhandenen Vermittlungsserverpool terminiert werden kann oder eigenständige Vermittlungsserver erfordert, hängt davon ab, ob der E9-1-1-SBC mit einem Vermittlungsserverpool interagieren kann. Weitere Informationen finden Sie unter [M:N trunk in Skype for Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Medienumgehung und Vermittlungsserver

Die Medienumgehung ist eine Skype for Business Server-Funktion, mit der ein Administrator das Anrufrouting so konfigurieren kann, dass es direkt zwischen dem Benutzerendpunkt und dem PstN-Gateway (Public Switched Telephone Network) fließt, ohne den Vermittlungsserver zu durchlaufen. Die Medienumgehung verbessert die Anrufqualität, indem die Latenz, unnötige Übersetzung, das Risiko von Paketverlusten und die Anzahl potenzieller Fehlerpunkte reduziert werden. Wenn ein Remotestandort ohne Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, reduziert die Medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Remotestandort direkt an das lokale Gateway fließen können, ohne zuerst über die WAN-Verbindung zu einem Vermittlungsserver am zentralen Standort und zurück fließen zu müssen. Diese Reduzierung der Medienverarbeitung ergänzt auch die Fähigkeit des Vermittlungsservers, mehrere Gateways zu steuern.
  
Die Medienumgehung und die Anrufsteuerung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.
  
## <a name="topologies-for-mediation-server"></a>Topologien für Vermittlungsserver

Der Skype for Business Server, Vermittlungsserver, ist standardmäßig mit dem Standard Edition-Server, einem Front-End-Pool oder einer Survivable Branch Appliance ausgeführt. Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.
  
Wenn die Leistung ein Problem ist, ist es möglicherweise vorzuziehen, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool zu bereitstellen. Es wird auf jeden Fall ein eigenständiger Pool empfohlen, wenn Sie das SIP-Trunking bereitstellen. 
  
Wenn Sie direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway bereitstellen, das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger fea-mediation-pool erforderlich. Dies liegt daran, dass qualifizierte Gateways einen DNS-Lastenausgleich für einen Pool von Vermittlungsservern verwenden können und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen können.
  
Es wird außerdem empfohlen, den Vermittlungsserver in einem Front-End-Pool zu verbinden, wenn Sie IP-PBXs bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Anbieters für Internettelefonieserver herstellen, solange eine der folgenden Bedingungen erfüllt ist:
  
- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.
    
- Die IP-PBX-Anlage unterstützt keine Medienumgehung, aber der Front-End-Pool, der den Vermittlungsserver hosten soll, kann die Sprachtranscodierung für Anrufe verarbeiten, für die die Medienumgehung nicht gilt.
    
Sie können das Planungstool von Microsoft Lync Server 2013 verwenden, um zu bewerten, ob der Front-End-Pool, in dem Sie den Vermittlungsserver verbinden möchten, die Last bewältigen kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
Die folgende Abbildung zeigt eine einfache Topologie, die aus zwei Standorten besteht, die über eine WAN-Verbindung verbunden sind. Der Vermittlungsserver ist mit einem Front-End-Pool an Standort 1 ausgeführt. Die Vermittlungsserver an Standort 1 steuert sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2. In dieser Topologie ist die Medienumgehung global für die Verwendung von Standort- und Regioneninformationen aktiviert, und die Trunks zu den einzelnen PstN-Gateways (GW1 und GW2) sind für die Umgehung aktiviert.
  
**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![Sprachtopologie mit Vermittlungsserver-WAN-Gateway](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Die nächste Abbildung zeigt eine einfache Topologie, bei der der Vermittlungsserver im Front-End-Pool an Standort 1 verbunden ist und über eine direkte SIP-Verbindung mit der IP-PBX-Anlage an Standort 1 verfügt. In dieser Abbildung steuert der Vermittlungsserver auch ein PstN-Gateway an Standort 2. Angenommen, Skype for Business-Benutzer sind an Den Standorten 1 und 2 vorhanden. Gehen Sie außerdem davon aus, dass die IP-PBX-Anlage über einen zugeordneten Medienprozessor verfügt, der von allen Von Skype for Business-Endpunkten stammenden Medien durchlaufen werden muss, bevor sie an von der IP-PBX-Anlage kontrollierte Medienendpunkte gesendet wird. In dieser Topologie ist die Medienumgehung global für die Verwendung von Standort- und Regioneninformationen aktiviert, und für die Trunks zur Nebenstellenanlage und zum PstN-Gateway ist die Medienumgehung aktiviert.
  
**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![Wan-PBX-Anlage des Vermittlungsservers für die Sprachtopologie](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der der Vermittlungsserver mit dem SBC eines Anbieters für Internettelefoniedienste verbunden ist. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planungsentscheidungen für vermittlungsserver

In diesem Thema werden Planungsentscheidungen beschrieben, die Sie für ihre Vermittlungsserverbereitstellung treffen müssen.
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Collocated or Stand-alone Mediation Server?

Der Vermittlungsserver ist standardmäßig mit anderen Servern auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten verbunden. Die Anzahl der Festnetzanrufe( Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl der im Pool erforderlichen Computer hängt von folgenden Kriterien ab:
  
- Die Anzahl der Gateway-Peers, die der Vermittlungsserverpool steuert
    
- Die Zeiträume für hohen Datenverkehr über diese Gateways
    
- Der Prozentsatz der Anrufe, deren Medien den Vermittlungsserver umgehen
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die nicht für die Medienumgehung konfiguriert sind, sowie die Verarbeitung, die erforderlich ist, um Signalinteraktionen für die Anzahl der Zustellgespräche zu verarbeiten, die unterstützt werden müssen. Wenn nicht genügend CPU verfügbar ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. UND PSTN-Gateways, IP-PBX-Anlagen und SBCs müssen in Teilmengen aufgeteilt werden, die von den zugeordneten Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-PBX-Anlagen oder Session Border Controller (SBCs) bereitgestellt haben, die nicht die richtigen Funktionen für die Interaktion mit einem Pool von Vermittlungsservern unterstützen, einschließlich der folgenden, müssen sie einem eigenständigen Pool zugeordnet werden, der aus einem einzelnen Vermittlungsserver besteht:
  
- Durchführen eines Netzwerkschicht-DNS-Lastenausgleichs (Domain Name System) auf Vermittlungsservern in einem Pool (oder anderweitige einheitliches Routen des Datenverkehrs an alle Vermittlungsserver in einem Pool)
    
- Akzeptieren von Datenverkehr von jedem Vermittlungsserver in einem Pool
    
Sie können das Planungstool von Microsoft Lync Server 2013 verwenden, um zu bewerten, ob das Verbinden des Vermittlungsservers mit Ihrem Front-End-Pool die Last bewältigen kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
### <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Bei Bereitstellung von SIP-Trunks müssen Sie jedoch einen Vermittlungsserver an dem Standort bereitstellen, der als Endpunkt für die einzelnen Trunks dient. Bei Einsatz eines Vermittlungsservers am zentralen Standort zum Weiterleiten von Anrufen für eine IP-Nebenstellenanlage oder ein PSTN-Gateway an einem Zweigstellenstandort ist keine Medienumgehung erforderlich. Wenn Sie jedoch die Medienumgehung aktivieren können, verringert dies die Latenz des Medienpfads und verbessert die Medienqualität, da der Medienpfad nicht mehr zum Folgen des Signalpfads erforderlich ist. Die Medienumgehung verringert auch die Verarbeitungslast für den Pool.
  
> [!NOTE]
> Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur für Produkte und Versionen unterstützt, die im [Unified Communications Open Interoperability Program - Lync Server aufgeführt sind.](https://go.microsoft.com/fwlink/p/?LinkId=268730) 
  
Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Bei ausfallsicheren Zweigstellenstandorten wird davon ausgegangen, dass Anwesenheits- und Konferenzstandorte am Standort nicht ausfallsicher sind.) Anleitungen zur Planung von Zweigstellenstandorten für Sprachnachrichten finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
  
Wenn die IP-PBX-Anlage bei Interaktionen mit einer IP-PBX-Anlage frühe Medieninteraktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, können die ersten Wörter der Begrüßung für eingehende Anrufe von der IP-PBX-Anlage an Skype for Business-Endpunkte abgeschnitten werden. This issue can be severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete. Wenn dieses Verhalten vor sich geht, ist die Bereitstellung eines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit, die Beschneidung der ersten Wörter zu reduzieren.
  
Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.
  
> [!NOTE]
> Um die Medienleistung des eigenständigen Vermittlungsservers zu verbessern, sollten Sie rss (Receive-Side Scaling) auf den Netzwerkadaptern auf diesen Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter ["Receive-Side Scaling Enhancements in Windows Server".](https://go.microsoft.com/fwlink/p/?LinkId=268731) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zum Netzwerkadapter. 
  

