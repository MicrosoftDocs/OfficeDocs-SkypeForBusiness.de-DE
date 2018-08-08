---
title: MN Trunk in Skype für Business Server
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: 'Skype für Business Server Enterprise-VoIP unterstützt die m: n-Trunking zwischen Vermittlungsserver und Komponenten wie PSTN-Gateways, Session Border Controller und IP-Nebenstellenanlage.'
ms.openlocfilehash: 13c25bddcbd5870caf0240f043321605cc9ace81
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012156"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>M: n-Trunk in Skype für Business Server
 
Skype für Business Server Enterprise-VoIP unterstützt die m: n-Trunking zwischen Vermittlungsserver und Komponenten wie PSTN-Gateways, Session Border Controller und IP-Nebenstellenanlage.
  
Skype für Business Server unterstützt größere Flexibilität in der Definition eines Trunks für die Weiterleitung von Gesprächen aus früheren Versionen. Ein Trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver und listening Portnummer mit einem Gateway und eine Portnummer listening. Dies bedeutet Folgendes: ein Vermittlungsserver kann mehrere Trunks mit dem gleichen Gateway; haben ein Vermittlungsserver kann mehrere Trunks mit verschiedenen Gateways aufweisen; dagegen kann ein Gateway mehrere Trunks mit unterschiedlichen Vermittlungsserver haben.
  
Sie müssen noch einen stammtrunk erstellen bei jeder Verwendung des Topologie-Generator zum Adde ein Gateway zur Topologie. Die Anzahl der Gateways, die einem bestimmten Mediation Server behandeln können hängt von der Kapazität des Servers während der Spitzenzeiten ausgelastet. Wenn Sie einen Vermittlungsserver auf Hardware, die die überschreitet die mindesthardwareanforderungen für Skype für Business-Server bereitstellen, wie beschrieben unter [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), klicken Sie dann die Schätzung des wie viele active keine Umgehung Anrufe ein eigenständigen Vermittlungsserver behandeln können ungefähr 1000 Anrufe ist. Bei der Bereitstellung auf Hardware Besprechung dieser Spezifikationen, der Vermittlungsserver wird erwartet, dass transcodieren ausführen, aber weiterhin Anrufe für mehrere Gateways weiterleiten, auch wenn die Gateways nicht unterstützen die medienumgehung.
  
Beim Definieren einer Route für Anrufe, geben Sie den Trunks dieser Route zugeordnet, aber keine angeben die Vermittlungsserver dieser Route zugeordnet sind. Verwenden Sie stattdessen Topologie-Generator zum Vermittlungsserver Trunks zuzuordnen. Mit anderen Worten, routing bestimmt, welche Trunk für einen Anruf zu verwendenden und, anschließend wird der Vermittlungsserver zugeordnet, Trunk die Signale für dieses Aufrufs gesendet.
  
Der Vermittlungsserver kann als Pool bereitgestellt werden. In diesem Pool mit einem Front-End-Pool verbunden werden, oder es als eigenständigen Pool bereitgestellt werden kann. Wenn Sie einen Vermittlungsserver mit einem Front-End-Pool verbunden ist, kann die Größe des Pools höchstens 12 (die Begrenzung der Größe des Registrar-Pools) sein. Gesamtheit dieser neuen Funktionen erhöhen die Zuverlässigkeit und Flexibilität bei der Bereitstellung für Vermittlungsserver, jedoch erfordern zugeordnete-Funktionen in der folgenden Peer-Entitäten:
  
- **PSTN-Gateway.** Eine Skype Business Server qualifizierten Gateways implementiert werden muss DNS-Lastenausgleich, wodurch ein Gateway qualifizierten Telefonfestnetz Network (PSTN), die als ein System zum Lastenausgleich für einen Pool von Vermittlungsservern und auf diese Weise einen Lastenausgleich Anrufe über den gesamten Pool fungiert .
    
- **Session Border Controller.** Für einen SIP-Trunk ist die Peer-Entität einer Session Border Controller (SBC) bei einem Internet Telephony Service Provider. In der Richtung aus dem Pool Vermittlungsserver an den SBC kann der SBC Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung von den SBC auf den Pool kann Datenverkehr an einem beliebigen Vermittlungsserver im Pool gesendet werden. Eine Methode hierfür ist über DNS-Lastenausgleich, wenn vom Dienstanbieter und SBC unterstützt. Eine Alternative ist die IP-Adressen alle Vermittlungsserver im Pool Geben Sie dem Dienstanbieter und der Dienstanbieter wird bereitstellen diese in ihren SBC als einen separaten SIP-Trunk für jeden Vermittlungsserver. Der Dienstanbieter behandelt den Lastenausgleich für eigene Server. Nicht alle Dienstanbieter oder SBCs können diese Funktionen unterstützt. Darüber hinaus kann der Dienstanbieter für diese Funktion sehr berechnen. Jeder SIP-Trunk zu den SBC fallen in der Regel eine monatliche Gebühr an.
    
- **IP-Nebenstellenanlage.** In der Richtung aus dem Pool Mediation Server auf die IP-PBX-SIP-Beendigung kann die IP-Nebenstellenanlage Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung auf den Pool aus der IP-Nebenstellenanlage kann Datenverkehr an einem beliebigen Vermittlungsserver im Pool gesendet werden. Da die meisten IP-PBXs keine DNS-Lastenausgleich unterstützen, wird empfohlen, einzelne direkte SIP-Verbindungen aus der IP-PBX mit jedem Vermittlungsserver im Pool definiert werden. In diesem Fall führt die IP-Nebenstellenanlage den eigenen Lastenausgleich durch, indem der Datenverkehr über die gesamte Trunkgruppe verteilt wird. Dabei wird davon ausgegangen, dass für die IP-Nebenstellenanlage ein konsistenter Satz an Routingregeln für die Trunkgruppe definiert wurde. Ob ein bestimmtes unterstützt IP-Nebenstellenanlage dieses Trunk Gruppe Konzept und wie sie mit der IP-Nebenstellenanlage des eigenen Redundanz überschneidet und clustering-Architektur muss festgelegt werden, bevor Sie entscheiden können, ob ein Vermittlungsserver Cluster ordnungsgemäß mit einer IP-Nebenstellenanlage interagieren kann.
    
Ein vermittlungsserverpool benötigen eine einheitliche Ansicht des Peer-Gateways, mit dem sie interagiert. Das bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher Zugriff auf dieselbe Definition des Peergateways erhalten und dass für alle Mitglieder die gleiche Wahrscheinlichkeit einer Interaktion mit dem Gateway für ausgehende Anrufe besteht. Aus diesem Grund besteht keine Möglichkeit, den Pool segmentieren, sodass nur bestimmte gatewaypeers für ausgehende Anrufe einige Vermittlungsserver kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Vermittlungsserver verwendet werden. Dies wäre z. B. der Fall, wenn die entsprechenden Funktionen zur Interaktion von PSTN-Gateways, SIP-Trunks oder IP-Nebenstellenanlagen mit einem Pool (wie zuvor in diesem Thema besprochen) nicht verfügbar sind.
  
Eine bestimmte PSTN-Gateways, IP-Nebenstellenanlage oder SIP-Trunk-Peer kann an mehrere Vermittlungsserver oder Trunks weiterleiten. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern können, hängt von der Anzahl der Anrufe, die die medienumgehung verwenden. Wenn eine große Anzahl von Anrufen die medienumgehung verwenden, können einen Vermittlungsserver im Pool viele weitere Anrufe, behandeln, da nur Signalisierung Layer Verarbeitung erforderlich ist. 
  

