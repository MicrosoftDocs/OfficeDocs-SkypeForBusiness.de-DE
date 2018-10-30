---
title: 'Lync Server 2013: M:N-Trunk'
TOCTitle: M:N-Trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398971(v=OCS.15)
ms:contentKeyID: 49295618
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# M:N-Trunk in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Lync Server 2013 ist im Vergleich zu früheren Versionen flexibler bezüglich der Definition eines Trunks zu Anrufweiterleitungszwecken. Bei einem Trunk handelt es sich um eine logische Zuordnung zwischen einem Vermittlungsserver und einer Überwachungsportnummer mit einem Gateway und einer Überwachungsportnummer. Dies bedeutet Folgendes: Ein Vermittlungsserver kann mehrere Trunks zum selben Gateway aufweisen; ein Vermittlungsserver kann mehrere Trunks zu verschiedenen Gateways aufweisen; umgekehrt kann ein Gateway mehrere Trunks zu verschiedenen Vermittlungsservern aufweisen.

Ein Strammtrunk muss weiterhin erstellt werden, wenn der Lync-Topologie mit dem Topologie-Generator ein Gateway hinzugefügt wird. Die Anzahl von Gateways, die ein Vermittlungsserver steuern kann, richtet sich nach der Verarbeitungskapazität des Servers zu Spitzenzeiten. Wenn Sie einen Vermittlungsserver auf Hardware bereitstellen, die die Mindestanforderungen für Hardware für Lync Server 2013 überschreitet (siehe [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation), kann ein eigenständiger Vermittlungsserver etwa 1.000 aktive Anrufe ohne Medienumgehung verarbeiten. Bei der Bereitstellung auf Hardware mit diesen Spezifikationen führt der Vermittlungsserver eine Transcodierung durch, routet jedoch weiterhin Anrufe für mehrere Gateways, auch wenn die Gateways keine Medienumgehung unterstützen.

Wenn Sie eine Anrufroute definieren, geben Sie die Trunks an, die dieser Route zugeordnet sind. Sie geben jedoch nicht an, welche Vermittlungsserver dieser Route zugeordnet sind. Stattdessen verwenden Sie den Topologie-Generator zum Zuordnen von Trunks zu Vermittlungsservern. Anders ausgedrückt: Das Routing legt den für einen Anruf zu verwendenden Trunk fest, und anschließend wird dem Vermittlungsserver, der diesem Trunk zugeordnet ist, das Signal für diesen Anruf gesendet.

Der Vermittlungsserver kann als Pool bereitgestellt werden; dieser Pool kann gemeinsam mit einem Front-End-Pool ausgeführt oder als eigenständiger Pool bereitgestellt werden. Wird ein Vermittlungsserver gemeinsam mit einem Front-End-Pool ausgeführt, gilt eine maximale Poolgröße von 12 (die Größenbegrenzung für den Registrierungsstellenpool). Diese neuen Funktionen erhöhen die Zuverlässigkeit und Flexibilität der Bereitstellung für Vermittlungsserver, erfordern jedoch entsprechende Funktionen der folgenden Peerentitäten:

  - **PSTN-Gateway.** Ein für Lync Server 2013 qualifiziertes Gateway muss den DNS-Lastenausgleich implementieren, wodurch ein qualifiziertes PSTN-Gateway als Gerät zum Lastenausgleich für einen Pool von Vermittlungsservern fungieren und Anrufe im Pool verteilen kann.

  - **Session Border Controller (SBC).** Bei einem SIP-Trunk ist die Peerentität ein SCB (Session Border Controller) beim Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP). In Richtung vom Vermittlungsserverpool zum SBC kann der SBC Verbindungen von jedem Vermittlungsserver im Pool empfangen. In Richtung vom SBC zum Pool kann der Datenverkehr an jeden Vermittlungsserver im Pool gesendet werden. Dies lässt sich z. B. über den DNS-Lastenausgleich erreichen, wenn dieser vom Dienstanbieter und SBC unterstützt wird. Alternativ können dem Dienstanbieter die IP-Adressen aller Vermittlungsserver im Pool übermittelt werden. Der Dienstanbieter kann diese dann im SBC als separaten SIP-Trunk für jeden Vermittlungsserver bereitstellen. In diesem Fall übernimmt der Dienstanbieter den Lastenausgleich für die eigenen Server. Eventuell unterstützen nicht alle Dienstanbieter oder SBCs diese Funktionen. Darüber hinaus erhebt der Dienstanbieter möglicherweise eine zusätzliche Gebühr für diese Funktion. In der Regel fällt für jeden SIP-Trunk zum SBC eine monatliche Gebühr an.

  - **IP-Nebenstellenanlage.** In Richtung vom Vermittlungsserverpool zum SIP-Endpunkt der IP-Nebenstellenanlage kann die IP-Nebenstellenanlage Verbindungen von jedem Vermittlungsserver im Pool empfangen. In Richtung von der IP-Nebenstellenanlage zum Pool kann der Datenverkehr an jeden Vermittlungsserver im Pool gesendet werden. Da die meisten IP-Nebenstellenanlagen keinen DNS-Lastenausgleich unterstützen, wird empfohlen, einzelne direkte SIP-Verbindungen von der IP-Nebenstellenanlage zu jedem Vermittlungsserver im Pool zu definieren. In diesem Fall führt die IP-Nebenstellenanlage den eigenen Lastenausgleich durch, indem der Datenverkehr über die gesamte Trunkgruppe verteilt wird. Dabei wird davon ausgegangen, dass für die IP-Nebenstellenanlage ein konsistenter Satz an Routingregeln für die Trunkgruppe definiert wurde. Ob eine bestimmte IP-Nebenstellenanlage dieses Konzept für Trunkgruppen unterstützt und wie dieses mit der eigenen Redundanz- und Clusteringarchitektur der IP-Nebenstellenanlage funktioniert, muss ermittelt werden, bevor Sie entscheiden, ob ein Vermittlungsservercluster ordnungsgemäß mit der IP-Nebenstellenanlage interagieren kann.

Ein Vermittlungsserverpool erfordert eine einheitliche Sicht des Peergateways für die Interaktion. Das bedeutet, dass alle Mitglieder des Pools über den Konfigurationsspeicher Zugriff auf dieselbe Definition des Peergateways erhalten und dass für alle Mitglieder die gleiche Wahrscheinlichkeit einer Interaktion mit dem Gateway für ausgehende Anrufe besteht. Demzufolge kann der Pool nicht in Segmente aufgeteilt werden, sodass einige Vermittlungsserver bei ausgehenden Anrufen nur mit bestimmten Gatewaypeers kommunizieren. Falls die Notwendigkeit einer solchen Segmentierung besteht, muss ein separater Vermittlungsserverpool verwendet werden. Dies wäre z. B. der Fall, wenn die entsprechenden Funktionen zur Interaktion von PSTN-Gateways, SIP-Trunks oder IP-Nebenstellenanlagen mit einem Pool (wie zuvor in diesem Thema besprochen) nicht verfügbar sind.

Ein bestimmtes PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SIP-Trunkpeer kann an mehrere Vermittlungsserver oder Trunks geroutet werden. Die Anzahl von Gateways, die ein bestimmter Vermittlungsserverpool steuern kann, hängt von der Anzahl von Anrufen ab, die die Medienumgehung verwenden. Wenn die Medienumgehung für eine große Anzahl von Anrufen verwendet wird, kann ein Vermittlungsserver im Pool sehr viel mehr Anrufe verarbeiten, da nur eine Verarbeitung auf Signalebene erforderlich ist.

