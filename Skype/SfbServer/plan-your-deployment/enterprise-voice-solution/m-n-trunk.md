---
title: MN trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice unterstützt M:N Trunking zwischen Mediation Server und Komponenten wie PSTN-Gateways, Session Border Controllers und IP-PBX.
ms.openlocfilehash: d9a4a4f08f71cf00e079a5fe9fc5598380936474
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802735"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>M:N trunk in Skype for Business Server
 
Skype for Business Server Enterprise Voice unterstützt M:N Trunking zwischen Mediation Server und Komponenten wie PSTN-Gateways, Session Border Controllers und IP-PBX.
  
Skype for Business Server unterstützt eine größere Flexibilität bei der Definition eines Trunks für Anruf Weiterleitungs Zwecke aus früheren Versionen. Ein trunk ist eine logische Zuordnung zwischen einem Vermittlungs Server und einer Abhör Portnummer mit einem Gateway und einer Abhör Portnummer. Dies impliziert mehrere Dinge: ein Vermittlungs Server kann mehrere Trunks zum gleichen Gateway haben; ein Vermittlungs Server kann mehrere Trunks zu unterschiedlichen Gateways aufweisen. Umgekehrt kann ein Gateway mehrere Trunks zu verschiedenen Vermittlungsservern aufweisen.
  
Sie müssen immer noch einen Stamm Stamm erstellen, wenn Sie den Topologie-Generator verwenden, um ein Gateway zur Topologie ADDE. Die Anzahl der Gateways, die ein bestimmter Vermittlungs Server verarbeiten kann, hängt von der Verarbeitungskapazität des Servers während der Spitzenzeiten ab. Wenn Sie einen Vermittlungs Server auf Hardware bereitstellen, die die Mindestanforderungen für die Hardware für Skype for Business Server überschreitet, wie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)beschrieben, ist die Schätzung, wie viele aktive nicht-Bypass-Anrufe ein eigenständiger Vermittlungsserver verarbeiten kann, ungefähr 1000 Anrufe. Bei der Bereitstellung auf Hardware, die diese Spezifikationen erfüllt, wird von dem Vermittlungs Server erwartet, dass Sie Transcodierung durchführen, aber weiterhin Anrufe für mehrere Gateways weiterleiten, auch wenn die Gateways keine medienumgehung unterstützen.
  
Wenn Sie eine Anrufroute definieren, geben Sie die Trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator, um Trunks mit Vermittlungsservern zu verknüpfen. Mit anderen Worten: das Routing bestimmt, welcher trunk für einen Anruf verwendet werden soll, und anschließend wird der dem Stamm zugeordnete Vermittlungs Server für diesen Anruf signalisiert.
  
Der Vermittlungs Server kann als Pool bereitgestellt werden. Dieser Pool kann mit einem Front-End-Pool zusammengestellt werden, oder er kann als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungs Server mit einem Front-End-Pool zusammengestellt wird, kann die Poolgröße höchstens 12 sein (die Grenze der Registrierungspool Größe). Zusammen genommen erhöhen diese neuen Funktionen die Zuverlässigkeits-und Bereitstellungsflexibilität für Vermittlungsserver, erfordern jedoch zugeordnete Funktionen in den folgenden Peer Entitäten:
  
- **PSTN-Gateway.** Ein von Skype for Business Server qualifiziertes Gateway muss den DNS-Lastenausgleich implementieren, wodurch ein qualifiziertes PSTN-Gateway (Public Switched Telephone Network) als Load-Balancer für einen Pool von Vermittlungsservern fungiert und dadurch Anrufe über den Pool geladen werden können. .
    
- **Session Border Controller.** Bei einem SIP-Trunk handelt es sich bei der Peer Entität um einen Session Border Controller (SBC) bei einem Internet-Telefoniedienst. In der Richtung vom vermittlungsserverpool zum SBC kann der SBC Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung vom SBC zum Pool kann der Datenverkehr an jeden Vermittlungs Server im Pool gesendet werden. Eine Möglichkeit, dies zu erreichen, ist der DNS-Lastenausgleich, wenn dieser vom Dienstanbieter und SBC unterstützt wird. Eine Alternative besteht darin, dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool zur Verfügung zu stellen, und der Dienstanbieter stellt diese in seinem SBC als separaten SIP-Trunk für jeden Vermittlungsserver bereit. Der Dienstanbieter übernimmt dann den Lastenausgleich für seine eigenen Server. Diese Funktionen werden nicht von allen Dienstanbietern oder SBCS unterstützt. Darüber hinaus kann der Dienstanbieter für diese Funktion zusätzliche Gebühren erheben. In der Regel wird für jeden SIP-Trunk des SBC eine monatliche Gebühr berechnet.
    
- **IP-Nebenstellenanlage.** In der Richtung vom vermittlungsserverpool zur IP-PBX-SIP-Kündigung kann die IP-PBX Verbindungen von einem beliebigen Vermittlungsserver im Pool empfangen. In der Richtung von der IP-PBX zum Pool kann der Datenverkehr an jeden Vermittlungs Server im Pool gesendet werden. Da die meisten IP-PBX-Anlagen den DNS-Lastenausgleich nicht unterstützen, empfehlen wir, einzelne direkte SIP-Verbindungen von der IP-PBX zu jedem Vermittlungs Server im Pool zu definieren. In diesem Fall führt die IP-Nebenstellenanlage den eigenen Lastenausgleich durch, indem der Datenverkehr über die gesamte Trunkgruppe verteilt wird. Dabei wird davon ausgegangen, dass für die IP-Nebenstellenanlage ein konsistenter Satz an Routingregeln für die Trunkgruppe definiert wurde. Ob eine bestimmte IP-Telefonanlage dieses trunk-Gruppenkonzept unterstützt und wie es mit der eigenen Redundanz und Clusterarchitektur der IP-PBX-Anlage überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungs Server Cluster ordnungsgemäß mit einer IP-Telefonanlage interagieren kann.
    
Ein Vermittlungs Server Pool muss eine einheitliche Ansicht des Peer Gateways aufweisen, mit dem es interagiert. Das bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher Zugriff auf dieselbe Definition des Peergateways erhalten und dass für alle Mitglieder die gleiche Wahrscheinlichkeit einer Interaktion mit dem Gateway für ausgehende Anrufe besteht. Daher gibt es keine Möglichkeit, den Pool zu segmentieren, sodass einige Vermittlungsserver nur mit bestimmten Gateway-Peers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies wäre z. B. der Fall, wenn die entsprechenden Funktionen zur Interaktion von PSTN-Gateways, SIP-Trunks oder IP-Nebenstellenanlagen mit einem Pool (wie zuvor in diesem Thema besprochen) nicht verfügbar sind.
  
Ein bestimmtes PSTN-Gateway, IP-PBX-oder SIP-Trunk-Peer kann zu mehreren Vermittlungsservern oder Trunks weitergeleitet werden. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die medienumgehung verwenden. Wenn bei einer großen Anzahl von Anrufen die medienumgehung verwendet wird, kann ein Vermittlungs Server im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung von Signalisierungs Ebenen erforderlich ist. 
  

