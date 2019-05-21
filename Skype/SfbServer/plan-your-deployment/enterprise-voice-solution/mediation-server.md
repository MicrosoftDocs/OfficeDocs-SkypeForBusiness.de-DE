---
title: Vermittlungsserver Komponente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Informationen zu Vermittlungsservern in Skype for Business Server, einschließlich der unterstützten Topologien und ihrer Beziehungen zu M:N Trunks, zur medienumgehung und zur Anrufsteuerung.
ms.openlocfilehash: 8c58e0b866d62e7dd1ea60888ba611d78328489f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276698"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Vermittlungsserver Komponente in Skype for Business Server
 
Informationen zu Vermittlungsservern in Skype for Business Server, einschließlich der unterstützten Topologien und ihrer Beziehungen zu M:N Trunks, zur medienumgehung und zur Anrufsteuerung.
  
Zur Bereitstellung von Enterprise-VoIP müssen Sie mindestens einen Vermittlungsserver bereitstellen. 
  
Der Vermittlungs Server übersetzt die Signalübertragung zwischen Ihrer internen Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem SIP-Stamm (Session Initiation Protocol). In einigen Bereitstellungen übersetzt sie auch die Medien selbst zwischen diesen Punkten.
  
Auf der Seite Skype for Business Server überwacht der Mediation Server eine einzige MTLS-Transportadresse (Mutual TLS). Auf der Gatewayseite überwacht der Vermittlungs Server alle zugehörigen Abhör Anschlüsse, die Trunks zugeordnet sind. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.
  
Wenn Sie auch über eine vorhandene öffentliche Branch Exchange (PBX) in Ihrer Umgebung verfügen, verarbeitet der Vermittlungs Server Anrufe zwischen Enterprise-VoIP-Benutzern und der Telefonanlage. Wenn es sich bei Ihrer Telefonanlage um eine IP-Telefonanlage handelt, können Sie eine direkte SIP-Verbindung zwischen der Telefonanlage und dem Vermittlungs Server herstellen. Wenn es sich bei Ihrer Telefonanlage um eine TDM-Telefonanlage (Time Division Multiplex) handelt, müssen Sie auch ein PSTN-Gateway zwischen dem Vermittlungs Server und der Telefonanlage bereitstellen.
  
Der Vermittlungsserver befindet sich standardmäßig mit dem Front-End-Server. Der Vermittlungs Server kann auch in einem eigenständigen Pool bereitgestellt werden.
  
## <a name="what-mediation-server-does"></a>Funktion des Vermittlungsservers

Die wichtigsten Funktionen des Vermittlungsservers lauten wie folgt:
  
- Verschlüsseln und Entschlüsseln von SRTP auf der Skype for Business-Server Seite. 
    
- Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über Mutual TLS
    
- Übersetzen von Medienströmen zwischen Skype for Business Server und dem Gateway-Peer des Vermittlungsservers.
    
- Herstellen von Verbindungen zwischen Clients außerhalb des Netzwerks und internen ICE-Komponenten, damit Medien NAT und Firewalls passieren können
    
- Fungiert als Vermittler für Anruf Flüsse, die von einem Gateway nicht unterstützt werden, beispielsweise Anrufe von Remotemitarbeitern auf einem Enterprise-VoIP-Clien.
    
- Verwenden des SIP-Trunking-Dienstanbieters für das Telefonfestnetz, sodass kein PSTN-Gateway erforderlich ist (gilt für Bereitstellungen mit SIP-Trunking)
    
Die folgende Abbildung zeigt die Signalisierungs-und Medienprotokolle, die vom Vermittlungs Server bei der Kommunikation mit einem einfachen PSTN-Gateway und der Enterprise-VoIP-Infrastruktur verwendet werden.
  
**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Vermittlungsserverprotokolle (Diagramm)](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Wenn Sie im Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungs Server TCP-oder RTP-RTCP (statt SRTP oder SRTCP) verwenden, empfiehlt es sich, Maßnahmen zu ergreifen, um die Sicherheit und den Datenschutz des Netzwerks zu gewährleisten. 
  
## <a name="mn-trunk"></a>M:N-Trunk

Skype for Business Server unterstützt die Flexibilität bei der Definition eines Trunks für Anrufrouting Zwecke. Bei einem Trunk handelt es sich um eine logische Zuordnung zwischen einem Vermittlungs Server und einer Abhör Portnummer mit einem Gateway und einer Abhör Portnummer. Dies impliziert mehrere Dinge: ein Vermittlungs Server kann mehrere Trunks zum gleichen Gateway haben; ein Vermittlungs Server kann mehrere Trunks zu unterschiedlichen Gateways aufweisen. Umgekehrt kann ein Gateway mehrere Trunks zu verschiedenen Vermittlungsservern aufweisen.
  
Sie müssen weiterhin einen Stamm Stamm erstellen, wenn Sie mit dem Topology Builder ein Gateway zu Ihrer Skype for Business-Topologie hinzufügen. Die Anzahl der Gateways, die ein bestimmter Vermittlungs Server verarbeiten kann, hängt von der Verarbeitungskapazität des Servers während der Spitzenzeiten ab. Wenn Sie einen Vermittlungsserver auf Hardware bereitstellen, die die Mindestanforderungen für die Hardware für Skype for Business Server erfüllt, wie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)beschrieben, kann ein eigenständiger Vermittlungsserver ungefähr 1000-Anrufe. Der Vermittlungs Server führt eine Transcodierung durch, aber weiterhin Anrufe für mehrere Gateways weiterleiten, selbst wenn die Gateways keine medienumgehung unterstützen.
  
Wenn Sie eine Anrufroute definieren, geben Sie die Trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator, um Trunks mit Vermittlungsservern zu verknüpfen. Mit anderen Worten: das Routing bestimmt, welcher trunk für einen Anruf verwendet werden soll, und anschließend wird der dem Stamm zugeordnete Vermittlungs Server für diesen Anruf signalisiert.
  
Der Vermittlungs Server kann als Pool bereitgestellt werden. Dieser Pool kann mit einem Front-End-Pool zusammengestellt werden, oder er kann als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungs Server mit einem Front-End-Pool zusammengestellt wird, kann die Poolgröße höchstens 12 sein (die Grenze der Registrierungspool Größe). Zusammen genommen erhöhen diese Funktionen die Zuverlässigkeit und Bereitstellungsflexibilität für Vermittlungsserver, erfordern aber ähnliche Funktionen in den folgenden Schritten:
  
- **PSTN-Gateway.** Ein von Skype for Business Server qualifiziertes Gateway muss den DNS-Lastenausgleich implementieren, wodurch ein qualifiziertes PSTN-Gateway (Public Switched Telephone Network) als Load-Balancer für einen Pool von Vermittlungsservern fungiert und dadurch Anrufe über den Pool geladen werden können. .
    
- **Session Border Controller.** Bei einem SIP-Trunk handelt es sich bei der Peer Entität um einen Session Border Controller (SBC) bei einem Internet-Telefoniedienst. In der Richtung vom vermittlungsserverpool zum SBC kann der SBC Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung vom SBC zum Pool kann der Datenverkehr an jeden Vermittlungs Server im Pool gesendet werden. Eine Möglichkeit, dies zu erreichen, ist der DNS-Lastenausgleich, wenn dieser vom Dienstanbieter und SBC unterstützt wird. Eine Alternative besteht darin, dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool zur Verfügung zu stellen, und der Dienstanbieter stellt diese in seinem SBC als separaten SIP-Trunk für jeden Vermittlungsserver bereit. Der Dienstanbieter übernimmt dann den Lastenausgleich für seine eigenen Server. Diese Funktionen werden nicht von allen Dienstanbietern oder SBCS unterstützt. Darüber hinaus kann der Dienstanbieter für diese Funktion zusätzliche Gebühren erheben. In der Regel wird für jeden SIP-Trunk des SBC eine monatliche Gebühr berechnet.
    
- **IP-Nebenstellenanlage.** In der Richtung vom vermittlungsserverpool zur IP-PBX-SIP-Kündigung kann die IP-PBX Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung von der IP-PBX zum Pool kann der Datenverkehr an jeden Vermittlungs Server im Pool gesendet werden. Da die meisten IP-PBX-Anlagen den DNS-Lastenausgleich nicht unterstützen, empfehlen wir, einzelne direkte SIP-Verbindungen von der IP-PBX zu jedem Vermittlungs Server im Pool zu definieren. In diesem Fall führt die IP-Nebenstellenanlage den eigenen Lastenausgleich durch, indem der Datenverkehr über die gesamte Trunkgruppe verteilt wird. Dabei wird davon ausgegangen, dass für die IP-Nebenstellenanlage ein konsistenter Satz an Routingregeln für die Trunkgruppe definiert wurde. Ob eine bestimmte IP-Telefonanlage dieses trunk-Gruppenkonzept unterstützt und wie es mit der eigenen Redundanz und Clusterarchitektur der IP-PBX-Anlage überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungs Server Cluster ordnungsgemäß mit einer IP-Telefonanlage interagieren kann.
    
Ein Vermittlungs Server Pool muss eine einheitliche Ansicht des Peer Gateways aufweisen, mit dem es interagiert. Das bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher Zugriff auf dieselbe Definition des Peergateways erhalten und dass für alle Mitglieder die gleiche Wahrscheinlichkeit einer Interaktion mit dem Gateway für ausgehende Anrufe besteht. Daher gibt es keine Möglichkeit, den Pool zu segmentieren, sodass einige Vermittlungsserver nur mit bestimmten Gateway-Peers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies wäre z. B. der Fall, wenn die entsprechenden Funktionen zur Interaktion von PSTN-Gateways, SIP-Trunks oder IP-Nebenstellenanlagen mit einem Pool (wie zuvor in diesem Thema besprochen) nicht verfügbar sind.
  
Ein bestimmtes PSTN-Gateway, IP-PBX-oder SIP-Trunk-Peer kann zu mehreren Vermittlungsservern oder Trunks weitergeleitet werden. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die medienumgehung verwenden. Wenn bei einer großen Anzahl von Anrufen die medienumgehung verwendet wird, kann ein Vermittlungs Server im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung von Signalisierungs Ebenen erforderlich ist. 
  
## <a name="call-admission-control-and-mediation-server"></a>Anrufsteuerung und Vermittlungsserver

Die Anrufsteuerung verwaltet Echtzeitsitzungen basierend auf der verfügbaren Bandbreite, um schlechte QoE-Resultate (Quality of Experience) für Benutzer in überlasteten Netzwerken zu verhindern. Um dies zu unterstützen, ist der Vermittlungsserver für die Bandbreitenverwaltung für die beiden Interaktionen auf der Skype for Business-Serverseite und auf der Gateway-Seite verantwortlich. Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung. Die Gateway-Peers (PSTN-Gateway, IP-PBX, SBC), mit denen der Vermittlungs Server auf der Gateway-Seite interagiert, unterstützen keine Skype for Business Server-Anrufsteuerung. Daher muss der Vermittlungs Server Bandbreiten Interaktionen im Auftrag seines Gateway-Peers verarbeiten. Wenn möglich, reserviert der Vermittlungs Server im Voraus eine Bandbreite. Wenn dies nicht möglich ist (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert. Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.
  
Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden. Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, der den Vermittlungs Server einbezieht, kann dieser Anruf keine medienumgehung verwenden.
  
Details zur medienumgehung oder zur Anrufsteuerung finden Sie unter [Planen der medienumgehung in Skype for Business](media-bypass.md) oder [Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver

Der Vermittlungs Server verfügt über erweiterte Funktionen, damit er mit erweiterten 9-1-1-Serviceanbietern (E9-1-1) richtig interagieren kann. Auf dem Vermittlungs Server ist keine spezielle Konfiguration erforderlich. Die für die E9-1-1-Interaktion erforderlichen SIP-Erweiterungen sind standardmäßig im SIP-Protokoll des Mediation-Servers für ihre Interaktionen mit einem Gateway-Peer (PSTN-Gateway, IP-Telefonanlage oder SBC eines Internet-Telefonie-Service-Anbieters) enthalten, einschließlich des E9-1-1-Diensts. Anbieter
  
Ob der SIP-Trunk zu einem E9-1-1-Dienstanbieter in einem vorhandenen Vermittlungs Server Pool beendet werden kann oder dass eigenständige Vermittlungsserver erforderlich sind, hängt davon ab, ob der E9-1-1-SBC mit einem Pool von Vermittlungsservern interagieren kann. Ausführliche Informationen finden Sie unter [M:N trunk in Skype for Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Medienumgehung und Vermittlungsserver

Media Bypass ist eine Skype for Business-Server Funktion, mit der ein Administrator das Anrufrouting so konfigurieren kann, dass es direkt zwischen dem Benutzer Endpunkt und dem PSTN-Gateway (Public Switched Telephone Network) läuft, ohne den Vermittlungs Server zu durchlaufen. Die medienumgehung verbessert die Anrufqualität, indem Latenz, unnötige Übersetzung, Möglichkeit des Paketverlusts und die Anzahl potenzieller Fehlerpunkte reduziert werden. Wenn eine Remotewebsite ohne Vermittlungs Server über eine oder mehrere WAN-Links mit eingeschränkter Bandbreite mit einem zentralen Standort verbunden ist, senkt die medienumgehung die Bandbreitenanforderung, indem Medien von einem Client an einem Remotestandort direkt an sein lokales Gateway weiter fließen können, ohne Zunächst müssen Sie über die WAN-Verbindung zu einem Vermittlungs Server am zentralen Standort und zurückfließen. Diese Verringerung der Medienverarbeitung ergänzt auch die Möglichkeit des Vermittlungsservers, mehrere Gateways zu steuern.
  
Die Medienumgehung und die Anrufsteuerung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.
  
## <a name="topologies-for-mediation-server"></a>Topologien für Vermittlungsserver

Der Skype for Business-Server, der Vermittlungsserver, ist standardmäßig mit dem Standard Edition-Server, einem Front-End-Pool oder einer Survivable Branch-Appliance ausgestattet. Alle Vermittlungsserver in einem Front-End-Pool müssen identisch konfiguriert sein.
  
Wenn die Leistung ein Problem ist, ist es möglicherweise vorzuziehen, einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitzustellen. Wenn Sie SIP-Trunking bereitstellen, wird auf jeden Fall die Bereitstellung eines eigenständigen Pools empfohlen. 
  
Wenn Sie direkte SIP-Verbindungen zu einem qualifizierten PSTN-Gateway bereitstellen, das medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungs Server Pool erforderlich. Dies liegt daran, dass qualifizierte Gateways in der Lage sind, den DNS-Lastenausgleich zu einem Pool von Vermittlungsservern durchzuführen und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen zu können.
  
Wir empfehlen außerdem, dass Sie den Vermittlungs Server in einem Front-End-Pool collocate, wenn Sie IP-PBX-Anlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Serveranbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:
  
- Die IP-PBX-oder SBC-Konfiguration ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver im Pool konfiguriert und kann den Datenverkehr gleicherweise an alle Vermittlungsserver im Pool weiterleiten.
    
- Die IP-PBX unterstützt keine medienumgehung, aber der Front-End-Pool, der den Vermittlungs Server hostet, kann die Sprachübertragung für Anrufe in die medienumgehung anwenden.
    
Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob der collocate, in dem Sie den Vermittlungsserver belegen möchten, die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.
  
Die folgende Abbildung zeigt eine einfache Topologie, bestehend aus zwei Websites, die über eine WAN-Verbindung verbunden sind. Der Vermittlungs Server befindet sich in einem Front-End-Pool an Standort 1. Die Vermittlungsserver an Standort 1 Steuern sowohl das PSTN-Gateway an Standort 1 als auch das Gateway an Standort 2. In dieser Topologie ist die medienumgehung Global für die Verwendung von Website-und Regionsinformationen aktiviert, und für die Trunks für jedes PSTN-Gateway (GW1 und GW2) ist die Umgehungsfunktion aktiviert.
  
**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![Sprach Topologie mit dem Vermittlungs Server-WAN-Gateway](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Die nächste Abbildung zeigt eine einfache Topologie, in der der Vermittlungs Server im Front-End-Pool von Standort 1 zusammengeführt wird und über eine direkte SIP-Verbindung mit der IP-PBX-Anlage an Standort 1 verfügt. In dieser Abbildung steuert der Vermittlungs Server auch ein PSTN-Gateway an Standort 2. Davon ausgehen, dass Skype for Business-Benutzer an beiden Standorten 1 und 2 vorhanden sind. Gehen Sie auch davon aus, dass die IP-Telefonanlage über einen zugehörigen medienprozessor verfügt, der von allen Medien, die von Skype for Business-Endpunkten stammen, durchlaufen werden muss, bevor Sie an Medien Endpunkte gesendet werden, die von der IP-PBX In dieser Topologie ist die medienumgehung Global für die Verwendung von Website-und Regionsinformationen aktiviert, und für die Trunks an die Telefonanlage und das PSTN-Gateway ist die medienumgehung aktiviert.
  
**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![Vermittlungs Server für sprach Topologie-WAN-PBX](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
Die letzte Abbildung in diesem Thema zeigt eine Topologie, in der der Vermittlungs Server mit dem SBC eines Internet Telefonie-Dienstanbieters verbunden ist. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planungsentscheidungen für Vermittlungsserver

In diesem Thema werden die Planungsentscheidungen beschrieben, die Sie für ihre Vermittlungs Server Bereitstellung treffen müssen.
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Oder eigenständigen Vermittlungs Server?

Der Vermittlungsserver befindet sich standardmäßig auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten. Die Anzahl von Anrufen über das Telefonfestnetz (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl erforderlicher Computer im Pool hängt von folgenden Faktoren ab:
  
- Die Anzahl der Gateway-Peers, die vom Vermittlungs Server Pool gesteuert werden
    
- Datenverkehr zu Spitzenzeiten, der über diese Gateways verarbeitet wird
    
- Der Prozentsatz der Anrufe, deren Medien den Vermittlungs Server umgehen
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und für A/V-Konferenzen, die nicht für eine Medienumgehung konfiguriert sind, sowie die erforderliche Leistung zur Verarbeitung von Signalinteraktionen für die Anzahl von Anrufen zu Spitzenzeiten, die unterstützt werden müssen. Wenn nicht genügend CPU vorhanden ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. und PSTN-Gateways, IP-PBX-Anlagen und SBCS müssen in Teilmengen aufgeteilt werden, die von den zusammengefassten Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-PBX-Anlagen oder SBCS (Session Border Controllers) bereitgestellt haben, die nicht die richtigen Funktionen für die Interaktion mit einem Pool von Mediations Servern, einschließlich der folgenden, unterstützen, müssen Sie einem eigenständigen Pool zugeordnet sein, bestehend aus eines einzelnen Vermittlungsservers:
  
- Durchführen von DNS (Domain Name System)-Lastenausgleich auf Netzwerkebene über Vermittlungsserver in einem Pool (oder anderweitiges Weiterleiten des Datenverkehrs an alle Vermittlungsserver in einem Pool)
    
- Akzeptieren von Datenverkehr von einem beliebigen Vermittlungs Server in einem Pool
    
Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob abstimmen dem Vermittlungsserver mit dem Front-End-Pool die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.
  
### <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können verwendet werden, um Anrufe für IP-PBX-oder PSTN-Gateways an Zweigstellen zu leiten. Wenn Sie jedoch SIP-Trunks bereitstellen, müssen Sie einen Vermittlungs Server an der Website bereitstellen, auf der jeder trunk beendet wird. Die Verwendung eines Vermittlungsservers an der zentralen Standort Route für Anrufe an ein IP-PBX-oder PSTN-Gateway an einer Zweigstelle erfordert keine medienumgehung. Wenn Sie die Medienumgehung jedoch aktivieren können, wird die Latenz für den Medienpfad reduziert und somit eine bessere Medienqualität erreicht, da der Medienpfad nicht mehr dem Signalpfad folgen muss. Die medienumgehung verringert auch die Verarbeitungsauslastung des Pools.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter [Unified Communications Open Interoperability Program-lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730)aufgeführt sind. 
  
Wenn die Stabilität des Zweigstellen Standorts erforderlich ist, muss eine Survivable Branch-Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway an der Zweigstelle bereitgestellt werden. (Die Annahme, dass die Stabilität des Zweigstellen Standorts davon ausgeht, dass Anwesenheit und Konferenzen auf der Website nicht belastbar sind.) Anleitungen zur Planung von Branch-Websites für VoIP finden Sie unter [Planen der Enterprise-VoIP-Resilienz in Skype for Business Server](enterprise-voice-resiliency.md).
  
Für Interaktionen mit einer IP-Telefonanlage, wenn die IP-Telefonanlage die frühen Medien Interaktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, können die ersten Wörter der Ansage für eingehende Anrufe von der IP-PBX zu Skype für abgeschnitten werden. Geschäfts Endpunkte. Dieses Problem kann gravierender sein, wenn ein Vermittlungs Server an einem zentralen Standort Anrufe an eine IP-PBX weiterleitet, bei denen die Route an einer Zweigstelle beendet wird, da für die Signalisierungs Ausführung mehr Zeit benötigt wird. Wenn dieses Verhalten auftritt, ist die Bereitstellungeines Vermittlungsservers auf der Verzweigungs Website die einzige Möglichkeit, das Clipping der ersten Wörter zu reduzieren.
  
Wenn Ihre zentrale Website über eine TDM-Telefonanlage verfügt oder wenn Ihre IP-Telefonanlage nicht die Notwendigkeit eines PSTN-Gateways beseitigt, müssen Sie ein Gateway auf der Anrufroute bereitstellen, die den Vermittlungs Server und die Telefonanlage verbindet.
  
> [!NOTE]
> Um die Medienqualität von eigenständigen Vermittlungsservern zu verbessern, sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter dieser Server aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter [Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731). Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter. 
  

