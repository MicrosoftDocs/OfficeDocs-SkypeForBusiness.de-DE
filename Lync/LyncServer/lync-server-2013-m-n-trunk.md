---
title: 'Lync Server 2013: m:n-trunk trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 699fe342005bda8142db11d49ebcafb1f89b8a58
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>M:n-trunk trunk in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Lync Server 2013 unterstützt größere Flexibilität bei der Definition eines Trunks für Anruf Weiterleitungs Zwecke aus früheren Versionen. Ein trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver und einer Abhör Portnummer mit einem Gateway und einer Überwachungs Portnummer. Dies impliziert mehrere Dinge: ein Vermittlungsserver kann mehrere Trunks zum gleichen Gateway haben; ein Vermittlungsserver kann mehrere Trunks zu unterschiedlichen Gateways haben; Umgekehrt kann ein Gateway über mehrere Trunks zu unterschiedlichen Vermittlungsservern verfügen.

Ein Stamm trunk muss weiterhin erstellt werden, wenn der lync-Topologie mithilfe des Topologie-Generators ein Gateway hinzugefügt wird. Die Anzahl der Gateways, die ein bestimmter Vermittlungsserver verarbeiten kann, hängt von der Verarbeitungskapazität des Servers in Spitzenzeiten ab. Wenn Sie eine Vermittlungsserver auf Hardware bereitstellen, die die minimalen Hardwareanforderungen für lync Server 2013 überschreitet, wie in der unter [stützten Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation beschrieben, kann die Schätzung der Anzahl der aktiven nicht-Umgehungs Aufrufe einer eigenständigen Vermittlungsserver etwa 1000 Anrufe verarbeiten. Bei der Bereitstellung auf Hardware, die diese Spezifikationen erfüllt, wird von der Vermittlungsserver erwartet, dass Sie Transcoding durchführen, aber Anrufe für mehrere Gateways weiterleiten, auch wenn die Gateways keine medienumgehung unterstützen.

Beim Definieren einer Anrufroute geben Sie die Trunks an, die dieser Route zugeordnet sind, aber Sie geben nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Verwenden Sie stattdessen den Topologie-Generator, um Trunks mit Vermittlungsservern zu verknüpfen. Mit anderen Worten: das Routing bestimmt, welcher trunk für einen Anruf verwendet werden soll, und anschließend wird die dem trunk zugeordnete Vermittlungsserver die Signalisierung für diesen Anruf gesendet.

Die Vermittlungsserver kann als Pool bereitgestellt werden; Dieser Pool kann mit einem Front-End-Pool zusammengestellt werden, oder er kann als eigenständiger Pool bereitgestellt werden. Wenn ein Vermittlungsserver mit einem Front-End-Pool zusammengesetzt ist, kann die Poolgröße höchstens 12 sein (Grenzwert für die Größe des Registrierungsstellen Pools). Zusammen genommen verbessern diese neuen Funktionen die Zuverlässigkeit und Flexibilität der Bereitstellung für Vermittlungsserver, erfordern jedoch die zugehörigen Funktionen in den folgenden Peer Entitäten:

  - **PSTN-Gateway.** Ein lync Server 2013 qualifiziertes Gateway muss den DNS-Lastenausgleich implementieren, wodurch ein qualifiziertes PSTN-Gateway (Public Switched Telephone Network) als Lastenausgleich für einen Pool von Vermittlungsservern fungieren und somit Anrufe über den Pool Lastenausgleich ausführen kann.

  - **Sitzungs Rahmen Controller.** Bei einem SIP-Trunk handelt es sich bei der Peer-Entität um einen Session Border Controller (SBC) bei einem Internet Telefonie-Dienstanbieter. In Richtung vom Vermittlungsserver Pool zum SBC kann der SBC Verbindungen von beliebigen Vermittlungsserver im Pool empfangen. In Richtung vom SBC zum Pool kann der Datenverkehr an jede Vermittlungsserver im Pool gesendet werden. Eine Möglichkeit, dies zu erreichen, ist der DNS-Lastenausgleich, wenn dieser vom Dienstanbieter und SBC unterstützt wird. Eine Alternative besteht darin, dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool zu geben, und der Dienstanbieter stellt diese in seinem SBC als separaten SIP-Trunk für jeden Vermittlungsserver bereit. Der Dienstanbieter übernimmt dann den Lastenausgleich für die eigenen Server. Nicht alle Dienstanbieter oder SBCS können diese Funktionen unterstützen. Darüber hinaus kann der Dienstanbieter für diese Funktion zusätzliche Gebühren verlangen. Normalerweise wird für jeden SIP-Trunk zum SBC eine monatliche Gebühr erhoben.

  - **IP-Nebenstellenanlage.** In Richtung vom Vermittlungsserver Pool zur IP-PBX-SIP-Beendigung kann die IP-Nebenstellenanlage Verbindungen von beliebigen Vermittlungsserver im Pool empfangen. In Richtung von der IP-Nebenstellenanlage zum Pool kann der Datenverkehr an eine beliebige Vermittlungsserver im Pool gesendet werden. Da die meisten IP-Nebenstellenanlagen keinen DNS-Lastenausgleich unterstützen, wird empfohlen, einzelne direkte SIP-Verbindungen von der IP-Nebenstellenanlage zu jeder Vermittlungsserver im Pool zu definieren. Die IP-Nebenstellenanlage verarbeitet dann einen eigenen Lastenausgleich, indem der Datenverkehr über die Trunkgruppe verteilt wird. Es wird davon ausgegangen, dass die Trunkgruppe über einen konsistenten Satz von Routingregeln an der IP-Nebenstellenanlage verfügt. Ob eine bestimmte IP-PBX dieses Trunkgruppen Konzept unterstützt und wie die IP-Nebenstellenanlage mit der eigenen Redundanz und Clustering-Architektur überschneidet, muss ermittelt werden, bevor Sie entscheiden können, ob ein Vermittlungsserver Cluster ordnungsgemäß mit einer IP-Nebenstellenanlage interagieren kann.

Ein Vermittlungsserver Pool muss eine einheitliche Ansicht des Peer Gateways haben, mit dem es interagiert. Dies bedeutet, dass alle Mitglieder des Pools auf dieselbe Definition des Peer Gateways aus dem Konfigurationsspeicher zugreifen und gleichzeitig für ausgehende Anrufe interagieren. Daher gibt es keine Möglichkeit, den Pool so zu segmentieren, dass einige Vermittlungsserver nur mit bestimmten Gateway-Peers für ausgehende Anrufe kommunizieren. Wenn eine solche Segmentierung erforderlich ist, muss ein separater Pool von Vermittlungsservern verwendet werden. Dies ist beispielsweise der Fall, wenn die zugehörigen Funktionen in PSTN-Gateways, SIP-Trunks oder IP-Nebenstellenanlagen zur Interaktion mit einem Pool wie weiter oben in diesem Thema beschrieben nicht vorhanden sind.

Ein bestimmtes PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SIP-Trunk-Peer kann an mehrere Vermittlungsserver oder Trunks weitergeleitet werden. Die Anzahl der Gateways, die ein bestimmter Pool von Vermittlungsservern steuern kann, hängt von der Anzahl der Anrufe ab, die die medienumgehung verwenden. Wenn eine große Anzahl von Anrufen die medienumgehung verwendet, kann eine Vermittlungsserver im Pool viele weitere Anrufe verarbeiten, da nur die Verarbeitung von Signal Ebenen erforderlich ist.

</div>

<span> </span>

</div>

</div>

</div>

