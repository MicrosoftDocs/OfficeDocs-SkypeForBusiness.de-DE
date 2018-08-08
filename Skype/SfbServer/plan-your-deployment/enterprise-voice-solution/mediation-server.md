---
title: Vermittlungsserverkomponente in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: 'Informationen Sie zu Vermittlungsservern in Skype für Business Server, einschließlich der unterstützten Topologien und seine Relations m: n-Trunks, medienumgehung und anrufsteuerung.'
ms.openlocfilehash: 95feb3b419eacf77739dfed98d2eee70eb49dc06
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009193"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Vermittlungsserverkomponente in Skype für Business Server
 
Informationen Sie zu Vermittlungsservern in Skype für Business Server, einschließlich der unterstützten Topologien und seine Relations m: n-Trunks, medienumgehung und anrufsteuerung.
  
Zum Bereitstellen von Enterprise-VoIP müssen Sie mindestens einen Vermittlungsserver bereitstellen. 
  
Der Vermittlungsserver übersetzt Signale zwischen Ihrer internen Enterprise-VoIP-Infrastruktur und einem Gateway public switched Telephone Network (Telefonfestnetz PSTN) oder einen Trunk Session Initiation Protocol (SIP). In einigen Bereitstellungen übersetzt sie auch die Medien selbst zwischen diesen Punkten.
  
Klicken Sie auf die Skype für Business Server-Seite überwacht der Vermittlungsserver eine einzelne mutual TLS (MTLS) Transportadresse. Aufseiten des Gateways überwacht der Vermittlungsserver auf alle zugehörigen Überwachungsports Trunks zugeordnet. Alle qualifizierten Gateways müssen TLS unterstützen, können jedoch auch TCP verwenden. TCP wird für Gateways unterstützt, die keine Unterstützung für TLS bieten.
  
Wenn Sie einer vorhandenen Public Branch Exchange (PBX) als auch in Ihrer Umgebung verfügen, verarbeitet Vermittlungsserver Anrufe zwischen Enterprise-VoIP-Benutzern und der Nebenstellenanlage. Wenn der Nebenstellenanlage eine IP-Nebenstellenanlage ist, können Sie eine direkte SIP-Verbindung zwischen der Nebenstellenanlage und dem Vermittlungsserver erstellen. Wenn der Nebenstellenanlage eine Time Division Multiplex (TDM) Nebenstellenanlage ist, müssen Sie auch ein PSTN-Gateway zwischen Vermittlungsserver und der Nebenstellenanlage bereitstellen.
  
Der Vermittlungsserver ist standardmäßig mit dem Front-End-Server zusammengestellt. Der Vermittlungsserver kann auch in einem eigenständigen Pool bereitgestellt werden.
  
## <a name="what-mediation-server-does"></a>Funktion des Vermittlungsservers

Die wichtigsten Funktionen des Vermittlungsservers lauten wie folgt:
  
- Verschlüsseln und Entschlüsseln von SRTP auf die Skype für Business Server-Seite. 
    
- Übersetzen von SIP über TCP (für Gateways, die TLS nicht unterstützen) in SIP über Mutual TLS
    
- Übersetzen von mediendatenströmen zwischen Skype für Business Server und dem gatewaypeer des Vermittlungsservers.
    
- Herstellen von Verbindungen zwischen Clients außerhalb des Netzwerks und internen ICE-Komponenten, damit Medien NAT und Firewalls passieren können
    
- Fungiert als Mittler für Response, die ein Gateway nicht, wie Anrufe von remote Mitarbeiter auf einer Enterprise-VoIP-clien.t unterstützt werden
    
- Verwenden des SIP-Trunking-Dienstanbieters für das Telefonfestnetz, sodass kein PSTN-Gateway erforderlich ist (gilt für Bereitstellungen mit SIP-Trunking)
    
Die folgende Abbildung zeigt die Signal- und Medien, die vom Vermittlungsserver verwendet werden, bei der Kommunikation mit einem Basis PSTN-Gateway und der Enterprise-VoIP-Infrastruktur.
  
**Vom Vermittlungsserver verwendete Signal- und Medienprotokolle**

![Vermittlungsserverprotokolle (Diagramm)](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Wenn Sie auf das Netzwerk zwischen dem PSTN-Gateway und dem Vermittlungsserver TCP oder RTP/RTCP (anstatt SRTP oder SRTCP) verwenden, wird empfohlen, dass Sie Maßnahmen zur Sicherstellung der Sicherheit und Datenschutz des Netzwerks. 
  
## <a name="mn-trunk"></a>M:N-Trunk

Skype für Business Server unterstützt Flexibilität in der Definition eines Trunks für die Weiterleitung von Gesprächen. Ein Trunk ist eine logische Verknüpfung zwischen einem Vermittlungsserver und listening Portnummer ein, mit einem Gateway und eine listening Portnummer ein. Dies bedeutet Folgendes: ein Vermittlungsserver kann mehrere Trunks mit dem gleichen Gateway; haben ein Vermittlungsserver kann mehrere Trunks mit verschiedenen Gateways aufweisen; dagegen kann ein Gateway mehrere Trunks mit unterschiedlichen Vermittlungsserver haben.
  
Wenn Sie ein Gateway zu Ihrer Skype für Business Topologie mithilfe des Topologie-Generators hinzufügen, müssen Sie dennoch eine stammtrunk erstellen. Die Anzahl der Gateways, die einem bestimmten Mediation Server behandeln können hängt von der Kapazität des Servers während der Spitzenzeiten ausgelastet. Wenn Sie einen Vermittlungsserver auf Hardware, die die Mindestanforderungen an die Hardware für Skype für Business Server erfüllt gemäß [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)bereitstellen, können Sie einen eigenständigen Vermittlungsserver ungefähr behandeln 1000 Anrufe. Der Vermittlungsserver ist transcodieren ausführt, aber weiterhin Anrufe für mehrere Gateways weitergeleitet, selbst wenn die Gateways keine medienumgehung unterstützen.
  
Beim Definieren einer Route für Anrufe, geben Sie den Trunks dieser Route zugeordnet, aber keine angeben die Vermittlungsserver dieser Route zugeordnet sind. Verwenden Sie stattdessen Topologie-Generator zum Vermittlungsserver Trunks zuzuordnen. Mit anderen Worten, routing bestimmt, welche Trunk für einen Anruf zu verwendenden und, anschließend wird der Vermittlungsserver zugeordnet, Trunk die Signale für dieses Aufrufs gesendet.
  
Der Vermittlungsserver kann als Pool bereitgestellt werden. In diesem Pool mit einem Front-End-Pool verbunden werden, oder es als eigenständigen Pool bereitgestellt werden kann. Wenn Sie einen Vermittlungsserver mit einem Front-End-Pool verbunden ist, kann die Größe des Pools höchstens 12 (die Begrenzung der Größe des Registrar-Pools) sein. Ähnliche Funktionen in den folgenden nehmen, aber Gesamtheit diese Funktionen erhöhen die Zuverlässigkeit und Flexibilität bei der Bereitstellung für Vermittlungsserver:
  
- **PSTN-Gateway.** Eine Skype Business Server qualifizierten Gateways implementiert werden muss DNS-Lastenausgleich, wodurch ein Gateway qualifizierten Telefonfestnetz Network (PSTN), die als ein System zum Lastenausgleich für einen Pool von Vermittlungsservern und auf diese Weise einen Lastenausgleich Anrufe über den gesamten Pool fungiert .
    
- **Session Border Controller.** Für einen SIP-Trunk ist die Peer-Entität einer Session Border Controller (SBC) bei einem Internet Telephony Service Provider. In der Richtung aus dem Pool Vermittlungsserver an den SBC kann der SBC Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung von den SBC auf den Pool kann Datenverkehr an einem beliebigen Vermittlungsserver im Pool gesendet werden. Eine Methode hierfür ist über DNS-Lastenausgleich, wenn vom Dienstanbieter und SBC unterstützt. Eine Alternative ist die IP-Adressen alle Vermittlungsserver im Pool Geben Sie dem Dienstanbieter und der Dienstanbieter wird bereitstellen diese in ihren SBC als einen separaten SIP-Trunk für jeden Vermittlungsserver. Der Dienstanbieter behandelt den Lastenausgleich für eigene Server. Nicht alle Dienstanbieter oder SBCs können diese Funktionen unterstützt. Darüber hinaus kann der Dienstanbieter für diese Funktion sehr berechnen. Jeder SIP-Trunk zu den SBC fallen in der Regel eine monatliche Gebühr an.
    
- **IP-Nebenstellenanlage.** In der Richtung aus dem Pool Mediation Server auf die IP-PBX-SIP-Beendigung kann die IP-Nebenstellenanlage Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung auf den Pool aus der IP-Nebenstellenanlage kann Datenverkehr an einem beliebigen Vermittlungsserver im Pool gesendet werden. Da die meisten IP-PBXs keine DNS-Lastenausgleich unterstützen, wird empfohlen, einzelne direkte SIP-Verbindungen aus der IP-PBX mit jedem Vermittlungsserver im Pool definiert werden. In diesem Fall führt die IP-Nebenstellenanlage den eigenen Lastenausgleich durch, indem der Datenverkehr über die gesamte Trunkgruppe verteilt wird. Dabei wird davon ausgegangen, dass für die IP-Nebenstellenanlage ein konsistenter Satz an Routingregeln für die Trunkgruppe definiert wurde. Ob ein bestimmtes unterstützt IP-Nebenstellenanlage dieses Trunk Gruppe Konzept und wie sie mit der IP-Nebenstellenanlage des eigenen Redundanz überschneidet und clustering-Architektur muss festgelegt werden, bevor Sie entscheiden können, ob ein Vermittlungsserver Cluster ordnungsgemäß mit einer IP-Nebenstellenanlage interagieren kann.
    
Ein vermittlungsserverpool benötigen eine einheitliche Ansicht des Peer-Gateways, mit dem sie interagiert. Das bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher Zugriff auf dieselbe Definition des Peergateways erhalten und dass für alle Mitglieder die gleiche Wahrscheinlichkeit einer Interaktion mit dem Gateway für ausgehende Anrufe besteht. Aus diesem Grund besteht keine Möglichkeit, den Pool segmentieren, sodass nur bestimmte gatewaypeers für ausgehende Anrufe einige Vermittlungsserver kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Vermittlungsserver verwendet werden. Dies wäre z. B. der Fall, wenn die entsprechenden Funktionen zur Interaktion von PSTN-Gateways, SIP-Trunks oder IP-Nebenstellenanlagen mit einem Pool (wie zuvor in diesem Thema besprochen) nicht verfügbar sind.
  
Eine bestimmte PSTN-Gateways, IP-Nebenstellenanlage oder SIP-Trunk-Peer kann an mehrere Vermittlungsserver oder Trunks weiterleiten. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern können, hängt von der Anzahl der Anrufe, die die medienumgehung verwenden. Wenn eine große Anzahl von Anrufen die medienumgehung verwenden, können einen Vermittlungsserver im Pool viele weitere Anrufe, behandeln, da nur Signalisierung Layer Verarbeitung erforderlich ist. 
  
## <a name="call-admission-control-and-mediation-server"></a>Anrufsteuerung und Vermittlungsserver

Die Anrufsteuerung verwaltet Echtzeitsitzungen basierend auf der verfügbaren Bandbreite, um schlechte QoE-Resultate (Quality of Experience) für Benutzer in überlasteten Netzwerken zu verhindern. Um dies zu unterstützen, wird der Vermittlungsserver für die bandbreitenverwaltung für die zwei Interaktionen auf die Skype für die Business Serverseite und aufseiten des Gateways. Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung. Die gatewaypeers (PSTN-Gateways, IP-Nebenstellenanlage, SBC), die der Vermittlungsserver, aufseiten des Gateways interagiert unterstützen keine Skype anrufsteuerung Business Server. Der Vermittlungsserver muss daher Bandbreite Interaktionen im Namen seiner gatewaypeer verarbeiten. Wenn möglich, wird der Vermittlungsserver Bandbreite im Voraus zu reservieren. Wenn dies nicht möglich ist (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert. Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.
  
Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden. Wenn die anrufsteuerung für einen bestimmten Aufruf, die der Vermittlungsserver umfasst verwendet wird, kann nicht dieses Aufrufs medienumgehung einsetzen.
  
Ausführliche Informationen zur Umgehung oder anrufsteuerung, finden Sie unter [Plan für Medien in Skype für Unternehmen umgehen](media-bypass.md) oder [für die anrufsteuerung in Skype für Business Server planen](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 (erweitert) (E9-1-1) und Vermittlungsserver

Der Vermittlungsserver hat erweiterte Funktionen, damit es ordnungsgemäß mit erweiterten E9-1-1 (E9-1-1)-Dienstanbietern interagieren kann. Keine besondere Konfiguration ist auf dem Vermittlungsserver erforderlich. Die SIP-Erweiterungen für E9-1-1-Interaktionen erforderlich sind, werden standardmäßig in der Vermittlungsserver SIP-Transportprotokoll für die Interaktionen mit einem gatewaypeer (PSTN-Gateways, IP-Nebenstellenanlage oder der SBC von E9-1-1-Dienst einschließlich Internet Telefoniedienstanbieter enthalten Anbieter)
  
Gibt an, ob der SIP-Trunk an einen E9-1-1-Dienstanbieter kann auf einen vorhandenen vermittlungsserverpool beendet werden oder eigenständigen Vermittlungsserver erfordern abhängig, ob die E9-1-1-SBC einen Pool von Vermittlungsservern interagieren können. Weitere Informationen hierzu finden Sie unter [m: n-Trunk in Skype für Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Medienumgehung und Vermittlungsserver

Die medienumgehung ist eine Skype für Business Server-Funktion, die ein Administrator Konfigurieren des Routings ausgehender Anrufe direkt zwischen den Endpunkt des Benutzers und das Gateway public switched Telephone Network, (PSTN) geleitet, ohne den Vermittlungsserver durchlaufen, um ermöglicht. Die medienumgehung wird durch die Reduzierung von Latenz, unnötige Konvertierung, Möglichkeit Paketverlust und die Anzahl der potenziellen Fehlerquellen Anrufqualität verbessert. Bei ein Remotestandort ohne einen Vermittlungsserver über eine oder mehrere WAN-Verbindungen mit bandbreiteneinschränkungen mit einem zentralen Standort verbunden ist, senkt die medienumgehung Bandbreite von Medien von einem Client an einem Remotestandort direkt an die lokalen Gateway ohne Fluss aktivieren Zuerst müssen über das WAN flow link zu einem Vermittlungsserver am zentralen Standort und dann wieder. Diese Verringerung der Verarbeitung von Medien auch ergänzt den Vermittlungsserver Kontrolle über mehrere Gateways.
  
Die Medienumgehung und die Anrufsteuerung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden.
  
## <a name="topologies-for-mediation-server"></a>Topologien für Vermittlungsserver

Die Skype für Business Server Mediation Server wird standardmäßig mit Standard Edition-Server, einem Front-End-Pool oder Survivable Branch Appliance kombiniert. Alle Vermittlungsserver in einem Front-End-Pool muss identischer Weise konfiguriert werden.
  
In denen Leistung von Belang ist, kann es einen oder mehrere Vermittlungsserver in einem dedizierten eigenständigen Pool bereitstellen vorzuziehen sein. Wenn Sie SIP-Trunking bereitstellen, wird auf jeden Fall die Bereitstellung eines eigenständigen Pools empfohlen. 
  
Wenn Sie die direkte SIP-Verbindungen mit einem qualifizierten PSTN-Gateway, die die medienumgehung unterstützt bereitstellen und DNS-Lastenausgleich ist über einen eigenständigen Vermittlungsserver Pool nicht erforderlich. Dies liegt daran qualifizierten Gateways sind in der Lage, mit dem DNS-Lastenausgleich in einen Pool von Vermittlungsservern und können sie Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen.
  
Darüber hinaus sollten Sie verbinden den Vermittlungsserver auf einem Front-End-Pool, wenn Sie IP-Nebenstellenanlagen bereitgestellt haben oder die Verbindung zu einem Internet Telephony Server Provider Session Border Controller (SBC) als eine der folgenden Bedingungen erfüllt sind:
  
- Die IP-Nebenstellenanlage oder der SBC ist so konfiguriert, dass er Datenverkehr von einem beliebigen Vermittlungsserver im Pool empfängt und kann Datenverkehr einheitlich weiterleiten an alle Vermittlungsserver im Pool.
    
- Die IP-Nebenstellenanlage unterstützt keine medienumgehung, aber der Front-End-Pool, der Vermittlungsserver hostet, kann sprachtranscodierung für Anrufe, die die medienumgehung nicht anwendbar ist.
    
Sie können die Microsoft Lync Server 2013, Planungstool untersuchen, ob der Front-End-Pool, wo Sie den Vermittlungsserver verbinden möchten, die Last verarbeiten kann. Wenn Ihre Umgebung diesen Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen vermittlungsserverpool bereitstellen.
  
Die folgende Abbildung zeigt eine einfache Topologie bestehend aus zwei Websites, die über eine WAN-Verbindung verbunden sind. Vermittlungsserver wird auf einem Front-End-Pool an Standort 1 kombiniert. Der Vermittlungsserver an Standort 1 steuert das PSTN-Gateway an Standort 1 und das Gateway an Standort 2. In dieser Topologie die medienumgehung Global Standorten und Regionen verwenden aktiviert ist, und die Trunks an jedem PSTN-Gateway (GW1 und GW2) Umgehung aktiviert haben.
  
**Beispiel für über eine WAN-Leitung verbundene Standorte mit einem Vermittlungsserver an Standort 1 und einem PSTN-Gateway an Standort 2**

![VoIP-Topologie mit Vermittlungsserver und WAN-Gateway](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
Die folgende Abbildung zeigt eine einfache Topologie, bei denen Vermittlungsserver an Standort 1-Front-End-Pool verbunden ist und eine direkte SIP-Verbindung mit der IP-Nebenstellenanlage an Standort 1. In dieser Abbildung steuert die Mediation Server auch ein PSTN-Gateway an Standort 2. Angenommen, die Skype für Unternehmensbenutzer an Standorten 1 und 2 vorhanden sind. Außerdem wird vorausgesetzt, dass die IP-Nebenstellenanlage einen dazugehörige Medienprozessor verfügt, das alle Medien, die vor dem Senden von Skype für Business-Endpunkte stammen durchlaufen werden müssen Media-Endpunkten, die durch die IP-Nebenstellenanlage gesteuert. In dieser Topologie die medienumgehung Global Standorten und Regionen verwenden aktiviert ist, und die Trunks an PBX und PSTN-Gateway die medienumgehung aktiviert haben.
  
**Beispiel für Standorte, die über eine WAN-Leitung mit einem Vermittlungsserver an Standort 1 und einer Nebenstellenanlage an Standort 2 verbunden sind**

![VoIP-Topologie mit Vermittlungsserver und WAN-Festnetztelefonanlage](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
In diesem Thema die letzte Abbildung zeigt eine Topologie, in dem der Vermittlungsserver mit den SBC des Internet Telephony Service Provider verbunden ist. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planungsentscheidungen für Vermittlungsserver

In diesem Thema wird die Planung getroffenen Entscheidungen, die Sie für Ihre Bereitstellung Mediation Server vornehmen müssen,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Verbundenen oder eigenständigen Vermittlungsserver?

Vermittlungsserver wird standardmäßig auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten kombiniert. Die Anzahl von Anrufen über das Telefonfestnetz (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl erforderlicher Computer im Pool hängt von folgenden Faktoren ab:
  
- Die Anzahl von gatewaypeers, die der vermittlungsserverpool steuert
    
- Datenverkehr zu Spitzenzeiten, der über diese Gateways verarbeitet wird
    
- Der Prozentsatz an anrufen, deren Medien des Vermittlungsservers Umgehung
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und für A/V-Konferenzen, die nicht für eine Medienumgehung konfiguriert sind, sowie die erforderliche Leistung zur Verarbeitung von Signalinteraktionen für die Anzahl von Anrufen zu Spitzenzeiten, die unterstützt werden müssen. Wenn nicht genügend CPU vorhanden ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. und PSTN-Gateways, IP-Nebenstellenanlagen und SBCs in Untergruppen aufgeteilt werden, die durch die verbundenen Vermittlungsserver in einem Pool und den eigenständigen Vermittlungsserver in einen oder mehrere eigenständigen Pools gesteuert werden müssen.
  
Wenn Sie bereitgestellt haben, PSTN-Gateways, IP-PBX-Anlagen oder Session Border Controller (SBCs), die keine für die richtigen Funktionen Unterstützung für die Interaktion mit einem Pool von Vermittlungsservern, einschließlich der folgenden müssen sie einen eigenständigen Pool mit folgenden Komponenten zugeordnet werden soll eines einzelnen Vermittlungsservers:
  
- Durchführen der Vermittlungsschicht Domain Name System (DNS) Lastenausgleich über Mediation Server in einem Pool (oder anderweitige einheitliche Weiterleitung des Datenverkehrs an alle Vermittlungsserver in einem Pool)
    
- Akzeptieren von Datenverkehr von einem beliebigen Vermittlungsserver in einem pool
    
Können Sie die Microsoft Lync Server 2013, Planungstool für ausgewertet werden soll, ob die Verbindung des Vermittlungsservers mit den Front-End-Pool kann die Last verarbeiten. Wenn Ihre Umgebung diesen Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen vermittlungsserverpool bereitstellen.
  
### <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können für das Anrufrouting für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigniederlassungen verwendet werden. Wenn Sie SIP-Trunks bereitstellen, müssen Sie jedoch einen Vermittlungsserver am Standort bereitstellen, auf dem jeden Trunk beendet wird. Mit einem Vermittlungsserver an den zentralen Standort Weiterleitung von Anrufen für eine IP-Nebenstellenanlage oder PSTN-Gateway an einem Zweigstellenstandort erfordert nicht die Verwendung von Medien umgehen. Wenn Sie die Medienumgehung jedoch aktivieren können, wird die Latenz für den Medienpfad reduziert und somit eine bessere Medienqualität erreicht, da der Medienpfad nicht mehr dem Signalpfad folgen muss. Die medienumgehung verringert außerdem die Verarbeitungslast auf den Pool.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten unterstützt und Versionen am aufgeführten [Unified Communications Open Interoperability Program – Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Wenn Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einen Vermittlungsserver und ein Gateway am Zweigstellenstandort bereitgestellt werden. (Die Annahme mit Zweigstellenstandorte ist, dass die Anwesenheit und Konferenzen nicht am Standort ausfallsichere sind.) Anleitung zum Planen von VoIP Zweigstellenstandort finden Sie unter [Planen für Enterprise Voice Resiliency in Skype für Business Server](enterprise-voice-resiliency.md).
  
Für die Interaktion mit einer IP-Nebenstellenanlage können die IP-Nebenstellenanlage early Media-Interaktionen mit mehreren frühe Dialoge und RFC 3960 Interaktionen, nicht ordnungsgemäß unterstützt werden sich bei Zuschneiden des ersten Wörter der für eingehende Anrufe aus der IP-PBX Skype für die Begrüßung Business-Endpunkte. Dieses Problem kann Schweregrad, wenn einem Vermittlungsserver an einem zentralen Standort Weiterleiten von Anrufen für eine IP-Nebenstellenanlage beendet wird, in dem die Route an einem Zweigstellenstandort ist, da mehr Zeit benötigt wird, für die Durchführung Signale sein. Wenn Sie dieses Verhalten auftreten, ist die Bereitstellung eines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit zur Reduzierung des ersten Wörter clipping.
  
Schließlich müssen verfügt Ihre zentralen Standort eine TDM-Nebenstellenanlage oder der IP-Nebenstellenanlage kein PSTN-Gateway erforderlich ist, klicken Sie dann auf das Herstellen einer Verbindung mit Vermittlungsserver und der Nebenstellenanlage Route für Anrufe ein Gateway bereitstellen.
  
> [!NOTE]
> Um die Medienqualität von eigenständigen Vermittlungsservern zu verbessern, sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter dieser Server aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen hierzu finden Sie unter ["Receive-Side Skalierung Verbesserungen in Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter. 
  

