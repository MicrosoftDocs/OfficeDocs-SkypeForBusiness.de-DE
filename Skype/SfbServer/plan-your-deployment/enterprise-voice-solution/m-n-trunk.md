---
title: MN-Trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype for Business Server Enterprise-VoIP unterstützt M:N-Trunking zwischen Vermittlungsserver und Komponenten wie PSTN-Gateways, Session Border Controllern und IP-Nebenstellenanlage.
ms.openlocfilehash: 28f5d7e9aae5406f54104e3411ecec6ba65ab7f4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770123"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>M:N-Trunk in Skype for Business Server
 
Skype for Business Server Enterprise-VoIP unterstützt M:N-Trunking zwischen Vermittlungsserver und Komponenten wie PSTN-Gateways, Session Border Controllern und IP-Nebenstellenanlage.
  
Skype for Business Server unterstützt eine größere Flexibilität bei der Definition eines Trunks für Anrufweiterleitungszwecke aus früheren Versionen. Ein Trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver und einer Überwachungsportnummer mit einem Gateway und einer Überwachungsportnummer. Dies impliziert mehrere Dinge: Ein Vermittlungsserver kann mehrere Trunks zum gleichen Gateway haben; Ein Vermittlungsserver kann mehrere Trunks zu unterschiedlichen Gateways haben. Umgekehrt kann ein Gateway mehrere Trunks zu verschiedenen Vermittlungsservern haben.
  
Sie müssen immer noch einen Stammtrunk erstellen, wenn Sie den Topologie-Generator verwenden, um der Topologie ein Gateway hinzuzufügen. Die Anzahl der Gateways, die ein bestimmter Vermittlungsserver verarbeiten kann, hängt von der Verarbeitungskapazität des Servers während der Spitzenzeiten ab. Wenn Sie einen Vermittlungsserver auf Hardware bereitstellen, der die Mindesthardwareanforderungen für Skype for Business Server überschreitet, wie in den [Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)beschrieben, beträgt die Schätzung, wie viele aktive Anrufe ohne Umgehung ein eigenständiger Vermittlungsserver verarbeiten kann, etwa 1000 Anrufe. Bei der Bereitstellung auf Hardware, die diesen Spezifikationen entspricht, wird vom Vermittlungsserver eine Transcodierung erwartet, anrufe für mehrere Gateways werden jedoch weiterhin weitergeleitet, auch wenn die Gateways keine Medienumgehung unterstützen.
  
Beim Definieren einer Anrufroute geben Sie die trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator, um Trunks Vermittlungsservern zuzuordnen. Das Routing bestimmt also, welcher Trunk für einen Anruf verwendet werden soll, und anschließend wird dem diesem Trunk zugeordneten Vermittlungsserver die Signalisierung für diesen Anruf gesendet.
  
Der Vermittlungsserver kann als Pool bereitgestellt werden. Dieser Pool kann mit einem Front-End-Pool verbunden oder als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungsserver mit einem Front-End-Pool verbunden ist, kann die Poolgröße maximal 12 (der Grenzwert der Poolgröße der Registrierungsstelle) sein. Zusammengenommen erhöhen diese neuen Funktionen die Zuverlässigkeit und Bereitstellungsflexibilität für Vermittlungsserver, erfordern jedoch zugehörige Funktionen in den folgenden Peerentitäten:
  
- **PSTN-Gateway.** Ein Skype for Business Server qualifizierte Gateway muss einen DNS-Lastenausgleich implementieren, der es einem qualifizierten PSTN-Gateway (Public Switched Telephone Network) ermöglicht, als Lastenausgleich für einen Pool von Vermittlungsservern zu fungieren und dadurch Anrufe über den Pool zu verteilen.
    
- **Session Border Controller.** Bei einem SIP-Trunk ist die Peerentität ein Session Border Controller (SBC) bei einem Anbieter von Internettelefoniediensten. In richtung vom Vermittlungsserverpool zum SBC kann der SBC Verbindungen von jedem Vermittlungsserver im Pool empfangen. In der Richtung vom SBC zum Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Eine Methode, dies zu erreichen, ist der DNS-Lastenausgleich, sofern dies vom Dienstanbieter und SBC unterstützt wird. Eine Alternative besteht darin, dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool zu geben, und der Dienstanbieter stellt diese auf dem SBC als separaten SIP-Trunk für jeden Vermittlungsserver bereit. Der Dienstanbieter übernimmt dann den Lastenausgleich für seine eigenen Server. Nicht alle Dienstanbieter oder SBCs unterstützen diese Funktionen möglicherweise. Darüber hinaus kann der Dienstanbieter für diese Funktion zusätzliche Gebühren berechnen. In der Regel wird für jeden SIP-Trunk zum SBC eine monatliche Gebühr berechnet.
    
- **IP-Nebenstellenanlage.** In Richtung vom Vermittlungsserverpool zum IP-PBX-SIP-Ende kann die IP-Nebenstellenanlage Verbindungen von jedem Vermittlungsserver im Pool empfangen. In richtung von der IP-Nebenstellenanlage an den Pool kann Datenverkehr an einen beliebigen Vermittlungsserver im Pool gesendet werden. Da die meisten IP-PBXs keinen DNS-Lastenausgleich unterstützen, wird empfohlen, dass einzelne direkte SIP-Verbindungen von der IP-Nebenstellenanlage zu jedem Vermittlungsserver im Pool definiert werden. Die IP-Nebenstellenanlage übernimmt dann ihren eigenen Lastenausgleich, indem der Datenverkehr über die Trunkgruppe verteilt wird. Es wird davon ausgegangen, dass die Trunkgruppe über einen konsistenten Satz von Routingregeln an der IP-Nebenstellenanlage verfügt. Ob eine bestimmte IP-Nebenstellenanlage dieses Trunkgruppenkonzept unterstützt und wie es sich mit der Redundanz- und Clusterarchitektur der IP-Nebenstellenanlage überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungsservercluster ordnungsgemäß mit einer IP-Nebenstellenanlage interagieren kann.
    
Ein Vermittlungsserverpool muss über eine einheitliche Ansicht des Peergateways verfügen, mit dem er interagiert. Dies bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher auf die gleiche Definition des Peergateways zugreifen und wahrscheinlich auch für ausgehende Anrufe damit interagieren. Daher gibt es keine Möglichkeit, den Pool so zu segmentieren, dass einige Vermittlungsserver nur mit bestimmten Gatewaypeers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies wäre beispielsweise der Fall, wenn die zugehörigen Funktionen in PSTN-Gateways, SIP-Trunks oder IP-PBXs für die Interaktion mit einem Pool nicht vorhanden sind, wie weiter oben in diesem Thema beschrieben.
  
Ein bestimmtes PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SIP-Trunkpeer kann an mehrere Vermittlungsserver oder Trunks weitergeleitet werden. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die Medienumgehung verwenden. Wenn eine große Anzahl von Anrufen die Medienumgehung verwendet, kann ein Vermittlungsserver im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung der Signalschicht erforderlich ist. 
  

