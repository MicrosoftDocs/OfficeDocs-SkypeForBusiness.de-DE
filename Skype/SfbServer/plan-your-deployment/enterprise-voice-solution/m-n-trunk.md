---
title: MN-Trunk in Skype for Business Server
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype for Business Server Enterprise-VoIP unterstützt das M:N-Trunking zwischen Vermittlungsservern und Komponenten wie PSTN-Gateways, Session Border Controllern und IP-PBX.
ms.openlocfilehash: 9e51eb1a19904f45abdcab47af719a3ac14867bf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825485"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>M:N-Trunk in Skype for Business Server
 
Skype for Business Server Enterprise-VoIP unterstützt M:N-Trunking zwischen Vermittlungsservern und Komponenten wie PSTN-Gateways, Session Border Controllern und IP-PBX.
  
Skype for Business Server unterstützt mehr Flexibilität bei der Definition eines Trunks für Anrufroutingzwecke aus früheren Versionen. Ein Trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver und der Nummer des Abhörports mit einem Gateway und einer Nummer für den Abhörport. Dies impliziert mehrere Dinge: Ein Vermittlungsserver kann mehrere Trunks zum gleichen Gateway haben; Ein Vermittlungsserver kann mehrere Trunks zu unterschiedlichen Gateways haben; Umgekehrt kann ein Gateway mehrere Trunks zu unterschiedlichen Vermittlungsservern haben.
  
Sie müssen immer noch einen Stamm trunk erstellen, wenn Sie den Topologie-Generator verwenden, um der Topologie ein Gateway hinzuzufügen. Die Anzahl der Gateways, die von einem bestimmten Vermittlungsserver verarbeitet werden können, hängt von der Verarbeitungskapazität des Servers zu Spitzenzeiten ab. Wenn Sie einen Vermittlungsserver auf Hardware bereitstellen, die die Mindesthardwareanforderungen für Skype for Business Server überschreitet, wie in den Serveranforderungen für [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)beschrieben, beträgt die Schätzung, wie viele aktive Anrufe ohne Umgehung ein eigenständiger Vermittlungsserver verarbeiten kann, ca. 1000 Anrufe. Wenn der Vermittlungsserver auf Hardware bereitgestellt wird, die diesen Spezifikationen entspricht, wird erwartet, dass er transcodiert, aber dennoch Anrufe für mehrere Gateways weiterroutet, auch wenn die Gateways die Medienumgehung nicht unterstützen.
  
Beim Definieren einer Anrufroute geben Sie die dieser Route zugeordneten Trunks an, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator, um Trunks Vermittlungsservern zuzuordnen. Das Routing bestimmt also, welcher Trunk für einen Anruf verwendet werden soll, und anschließend wird dem diesem Trunk zugeordneten Vermittlungsserver die Signalisierung für diesen Anruf gesendet.
  
Der Vermittlungsserver kann als Pool bereitgestellt werden. Dieser Pool kann mit einem Front-End-Pool oder als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungsserver mit einem Front-End-Pool ausgeführt wird, kann die Poolgröße bis zu 12 (die Beschränkung der Größe des Registrierungspools) sein. Zusammen erhöhen diese neuen Funktionen die Zuverlässigkeit und Bereitstellungsflexibilität für Vermittlungsserver, erfordern jedoch zugeordnete Funktionen in den folgenden Peerentitäten:
  
- **PSTN-Gateway.** Ein qualifiziertes Skype for Business Server-Gateway muss einen DNS-Lastenausgleich implementieren, der es einem qualifizierten PSTN-Gateway (Public Switched Telephone Network) ermöglicht, als Lastenausgleich für einen Pool von Vermittlungsservern zu fungieren und dadurch einen Lastenausgleich für Anrufe über den Pool hinweg zu ermöglichen.
    
- **Session Border Controller.** Bei einem SIP-Trunk ist die Peerentität ein Session Border Controller (SBC) bei einem Anbieter von Internettelefoniediensten. In Richtung des Vermittlungsserverpools zum SBC kann der SBC Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In Richtung des SBC zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Eine Möglichkeit, dies zu erreichen, ist der DNS-Lastenausgleich, sofern dieser vom Dienstanbieter und SBC unterstützt wird. Alternativ können Sie dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool bereitstellen, und der Dienstanbieter wird diese in ihrem SBC als separater SIP-Trunk für jeden Vermittlungsserver bereitstellen. Der Dienstanbieter wird dann den Lastenausgleich für seine eigenen Server übernehmen. Nicht alle Dienstanbieter oder SBCs unterstützen diese Funktionen. Darüber hinaus kann der Dienstanbieter zusätzliche Gebühren für diese Funktion berechnen. In der Regel fallen für jeden SIP-Trunk zum SBC monatliche Gebühren an.
    
- **IP-PBX.** In richtung des Vermittlungsserverpools zur IP-PBX-SIP-Beendigung kann die IP-PBX-Anlage Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In Richtung der IP-PBX-Anlage zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Da die IP-PBXs keine Unterstützung für den DNS-Lastenausgleich bieten, empfiehlt es sich, einzelne direkte SIP-Verbindungen von der IP-PBX-Anlage zu jedem Vermittlungsserver im Pool zu definieren. Die IP-PBX-Anlage übernimmt dann einen eigenen Lastenausgleich, indem der Datenverkehr über die Trunkgruppe verteilt wird. Es wird davon ausgegangen, dass die Trunkgruppe über einen konsistenten Satz von Routingregeln an der IP-PBX-Anlage verfügt. Ob eine bestimmte IP-PBX-Anlage dieses Trunkgruppenkonzept unterstützt und wie es sich mit der eigenen Redundanz- und Clusterarchitektur der IP-PBX überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungsservercluster ordnungsgemäß mit einer IP-PBX-Anlage interagieren kann.
    
Ein Vermittlungsserverpool muss über eine einheitliche Ansicht des Peergateways verfügen, mit dem er interagiert. Dies bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher auf dieselbe Definition des Peergateways zugreifen und mit gleicher Wahrscheinlichkeit für ausgehende Anrufe damit interagieren. Daher gibt es keine Möglichkeit, den Pool so zu segmentieren, dass einige Vermittlungsserver nur mit bestimmten Gateway peers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies wäre beispielsweise der Fall, wenn die zugeordneten Funktionen in PSTN-Gateways, -SIP-Trunks oder IP-PBXs für die Interaktion mit einem Pool wie weiter oben in diesem Thema beschrieben nicht vorhanden sind.
  
Ein bestimmtes PSTN-Gateway, eine IP-PBX-Anlage oder ein SIP-Trunk-Peer kann an mehrere Vermittlungsserver oder Trunks geroutet werden. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die Medienumgehung verwenden. Wenn für eine große Anzahl von Anrufen die Medienumgehung verwendet wird, kann ein Vermittlungsserver im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung der Signalschicht erforderlich ist. 
  

